<template>
    <div class="mpp-all left-box-03">
            <h2 class="mp-title">{{ tcTitle }}</h2>
        <div class="mp-table">
            <template>
                <el-table :data="this.data" style="width: 100%" min-height="200" max-height="350" size="mini">
                    <el-table-column prop="number" label="序号">
                    </el-table-column>
                    <el-table-column prop="name" label="姓名" >
                    </el-table-column>
                    <el-table-column prop="handleType" label="业务类型">
                    </el-table-column>
                    <el-table-column prop="waitingTime" label="等待时间">
                    </el-table-column>
                </el-table>
            </template>
        </div>
    </div>
</template>

<script>
    export default {
        name: "time-turn",
        data(){
            return{
                tcTitle: "当前大厅排队信息",
                stompClient:'',
                timer:'',
                tableData: [
                    {
                        number: '001',
                        name: '112',
                        handleType: '5',
                        waitingTime: '7min'
                    }
                ],

            }
        },
        props:['data'],
        methods:{
            // headerStyle({row,rowIndex}){
            //     return 'table-th'
            // },
    },
 }
</script>

<style scoped>
    .left-box-03{
        min-height: 449px;
    }
</style>