<template>
    <div class="db-content">
        <img src="../assets/top-line.png" class="bg-img">
        <el-row>
            <!--左侧列表-->
            <el-col :span="6">
                <div class="left-box">
                    <v-ma></v-ma>
                    <v-tc></v-tc>
                    <v-tt :data="waitingInfo"></v-tt>
                </div>
            </el-col>
                <el-col :span="12">
                <div class="center-block">
                    <v-time></v-time>
                    <v-mapControl></v-mapControl>
                    <v-eline></v-eline>
                </div>
            </el-col>
            <el-col :span="6">
                <div class="right-box">
                    <v-ecircle></v-ecircle>
                    <v-ecount></v-ecount>
                    <v-ebar></v-ebar>
                </div>
            </el-col>
        </el-row>
    </div>
</template>


<script>
    import MA from './public/MppAll.vue'
    import TC from './public/TopCount.vue'
    import TT from './public/timeTurn.vue'
    import MapControl from './public/MapControl.vue'
    import TimeCheck from './public/TimeCheck.vue'
    import eLine from './public/eLine.vue'
    import eCircle from './public/eCircle.vue'
    import eCount from './public/eCount.vue'
    import eBar from './public/eBar.vue'


    // 使用websocket
    import SocketJS from 'sockjs-client';
    import Stomp from 'stompjs';

    export default {
        name: "d-b",
        data(){
            return{
                stompClient: '',
                timer: '',
                // 排队人数信息
                waitingInfo: [],
                // 设备处理步骤异常信息
                deviceStepExceptionInfo: [],
                // 机器状态信息
                deviceStateInfo: [],
                // 当前大厅排队人数
                numberOfQueues: []
            }
        },
        mounted(){
            this.initWebSocket();
        },
        beforeDestroy(){
            // 页面离开时候断开连接,清除定时器
            this.disconnect();
            // clearInterval(this.timer);
        },
        methods:{
            initWebSocket(){
                this.connection();
                let that =this;
                // 断开重连机制，尝试发送消息，捕获异常状态发生时重连
                // this.timer = setInterval(()=>{
                //     try{
                //         that.stompClient.send('text');
                //     }
                //     catch(err){
                //         console.log('断线了:',+err);
                //         that.connection();
                //     }
                // },10000)
            },
            connection(){
                // 建立连接对象
                let socket = new SocketJS('http://10.200.20.27:8085/webSocketServer');
                // 获取STOMP子协议的客户端对象
                this.stompClient = Stomp.over(socket);
                // 定义客户端的验证信息，按需求配置
                // let headers = {
                //     Authorization: ''
                // };
                // 向服务器发起websocket连接
                let that = this;
                this.stompClient.connect({},()=>{
                    this.stompClient.subscribe('/topic/deviceStateInfo',(msg)=>{ //订阅服务器端提供的topic
                        that.deviceStateInfo = JSON.parse(msg.body).data;
                        console.log('设备状态实时信息',this.deviceStateInfo)
                    });
                    this.stompClient.subscribe('/topic/waitingInfo',(msg)=>{
                        // 当前大厅排队人员
                        that.waitingInfo = JSON.parse(msg.body).data.queuingList;
                        // 当前大厅排队人数
                        that.numberOfQueues = JSON.parse(msg.body).data.numberOfQueues;
                        console.log('大厅排队信息',that.waitingInfo)
                    });
                    this.stompClient.subscribe('/topic/deviceStepExceptionInfo',(msg)=>{
                        console.log(msg);
                        // that.deviceStepExceptionInfo = JSON.parse(msg);
                        // console.log('设备处理步骤异常实时信息',that.deviceStepExceptionInfo);
                    });
                    // this.stompClient.send('/app/chat.addUser',
                    //     headers,
                    //     JSON.stringify({sender: '',chatType: 'JSON'})
                    // ) // 用户加入接口
                },(err)=>{
                    // 连接发生错误时候的处理函数
                    console.log('失败');
                    console.log(err);
                });
            }, //连接后台
            disconnect(){
                if(this.stompClient){
                    this.stompClient.disconnect();
                }
            }, //断开连接
        },
        components:{
            "v-ma": MA,
            "v-tc": TC,
            "v-tt": TT,
            'v-mapControl': MapControl,
            "v-time": TimeCheck,
            'v-eline': eLine,
            'v-ecircle': eCircle,
            'v-ecount': eCount,
            'v-ebar': eBar
        }
    }
</script>

<style scoped lang="scss">
    .db-content{
        width: 100%;
        height: auto;
        background: #020a1e;
        padding: 10px;
        .center-block{
            margin: 0 10px;
        }
    }
    .left-box{
        display: flex;
        flex-direction: column;
        .left-box-01{

        }
        .left-box-02{

        }
        .left-box-03{
            flex: 1
        }
    }
    .bg-img{
        width: 100%;
        position: absolute;
        height: 67px;
        display: block;
        left: 0;
        top: 54px;
    }
</style>