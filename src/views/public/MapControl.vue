<template>
    <div class="mpp-all">
        <div class="mp-title">{{title}}</div>
        <div class="MapControl">
            <div class="mc-box">
                <div class="content">
                    <div class="left-bar">
                        <div class="loader-container">
                            <span class="runner">
                                <div class="wave ripple warning">
                                    <div class="circle"></div>
                                    <div class="circle"></div>
                                    <div class="circle"></div>
                                </div>
                                <div class="msgbox">
                                    当前排队人数 {{ waitingPerson }}
                                </div>
                            </span>
                        </div>
                    </div>
                    <div class="right-content">
                        <div class="box">
                            <div class="map-center">
                                <!--背景-->
                                <div class="map-box">
                                    <div class="shadow-box-a"></div>
                                    <div class="shadow-box-b"></div>
                                </div>
                                <!--色块-->
                                <div class="map-machine">
                                    <div class="machine-list">
                                    <span class="machine-box mb001">
                                        <span class="left-bar"></span>
                                        <span class="right-bar">&nbsp;01</span>
                                    </span>
                                        <div class="desk dk001">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb002">
                                        <span class="left-bar"></span>
                                        <span class="right-bar">&nbsp;02</span>
                                    </span>
                                        <div class="desk dk002">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb003">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;03</span>
                                    </span>
                                        <div class="desk dk003">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb004">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;04</span>
                                </span>
                                        <div class="desk dk004">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                        <span class="machine-box mb005 warning">
                                            <span class="left-bar"></span>
                                            <span class="right-bar">&nbsp;05</span>
                                        </span>
                                        <div class="desk dk005">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb006">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;06</span>
                                </span>
                                        <div class="desk dk006">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb007">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;07</span>
                                </span>
                                        <div class="desk dk007">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb008">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;08</span>
                                </span>
                                        <div class="desk dk008">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb009">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;09</span>
                                </span>
                                        <div class="desk dk009">
                                            <img src="../../assets/unsit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb010">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;10</span>
                                </span>
                                        <div class="desk dk010">
                                            <img src="../../assets/sit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb011">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;11</span>
                                </span>
                                        <div class="desk dk011">
                                            <img src="../../assets/unsit.png">
                                        </div>
                                    </div>
                                    <div class="machine-list">
                                    <span class="machine-box mb012">
                                    <span class="left-bar"></span>
                                    <span class="right-bar">&nbsp;12</span>
                                </span>
                                        <div class="desk dk012">
                                            <img src="../../assets/unsit.png">
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "map-control",
        data(){
            return{
                title: '终端当前数据状态',
                progress: '',
                arrCount: [],
                waitingPerson: ''
            }
        },
        methods:{

        },
        mounted(){

        }
    }
</script>

<style scoped lang="scss">
    $mapControl: #2c4e76;
    $shadowColorA:#0b325e;
    $shadowColorB: #061e39;
    $machineColor: #00af53;
    $warningColor: #ae305a;
    .MapControl{
        margin: 0 10px;
        .mc-box{
            .title{
                color: #fff;
            }
            .content{
                margin: 10px 0;
                display: flex;
                flex-wrap: nowrap;
                .left-bar{
                    position: relative;
                    width: 10%;
                    .loader-container{
                        margin: 0 auto;
                        position: relative;
                        display: block;
                        width: 14px;
                        height: 400px;
                        background-image: linear-gradient( 0deg, rgb(0,231,179) 0%,rgb(237,212,0) 50%, rgb(242,34,0) 100%);
                        border-radius: 4px;
                        padding: 4px;
                        box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.25), 0 1px rgba(255, 255, 255, 0.08);
                        /*&:before{*/
                            /*content: '';*/
                            /*background: url("../../assets/stripes.png") 0 0 repeat;*/
                        /*}*/
                        .runner{
                            height: 67%;
                            width: 100%;
                            background: #031531;
                            position: absolute;
                            border-top-left-radius: 4px;
                            border-top-right-radius: 4px;
                            top: 0;
                            left: 0;
                            transition: 0.4s linear;
                            transition-property: width, background-color;
                            /*box-shadow: 0 0 1px 1px rgba(0, 0, 0, 0.25), inset 0 1px rgba(255, 255, 255, 0.1);*/
                            &:before{
                                content: '';
                                position: absolute;
                                top: 0;
                                left: 0;
                                right: 0;
                                bottom: 0;
                                /*border-radius: 4px 4px 0 0;*/
                            }
                            &:after{
                                content: '';
                                position: absolute;
                                top: 0;
                                left: 0;
                                right: 0;
                                z-index: 2;
                                bottom: 45%;
                                border-radius: 4px;
                            }
                        }
                    }
                }
                .right-content{
                    flex: 1;
                    width: 90%;
                    position: relative;
                    .box{
                        width: 400px;
                        margin: 0 auto;
                        .map-center{
                            min-height: 400px;
                            position: relative;
                            .map-box{
                                display: block;
                                width: 300px;
                                height: 200px;
                                background: $mapControl;
                                position: absolute;
                                left: 50px;
                                top: 100px;
                                &:before{
                                    content: '';
                                    top: -50px;
                                    width: 200px;
                                    position: absolute;
                                    border-color: transparent transparent $mapControl transparent;
                                    border-width: 0 50px 50px 50px;
                                    border-style: solid;
                                }
                                &:after{
                                    content: '';
                                    bottom: -50px;
                                    width: 200px;
                                    position: absolute;
                                    border-color: $mapControl transparent transparent transparent;
                                    border-width: 50px 50px 0 50px;
                                    border-style: solid;
                                }
                                .shadow-box-a {
                                    display: block;
                                    width: 180px;
                                    height: 130px;
                                    background: $shadowColorA;
                                    left: 60px;
                                    top: 35px;
                                    position: absolute;
                                    &:before {
                                        content: '';
                                        top: -30px;
                                        width: 120px;
                                        position: absolute;
                                        border-color: transparent transparent $shadowColorA transparent;
                                        border-width: 0 30px 30px 30px;
                                        border-style: solid;
                                    }
                                    &:after {
                                        content: '';
                                        bottom: -30px;
                                        width: 120px;
                                        position: absolute;
                                        border-color: $shadowColorA transparent transparent transparent;
                                        border-width: 30px 30px 0 30px;
                                        border-style: solid;
                                    }
                                }
                                .shadow-box-b {
                                    display: block;
                                    width: 160px;
                                    height: 120px;
                                    background: $shadowColorB;
                                    left: 70px;
                                    top: 40px;
                                    position: absolute;
                                    &:before {
                                        content: '';
                                        top: -30px;
                                        width: 110px;
                                        position: absolute;
                                        border-color: transparent transparent $shadowColorB transparent;
                                        border-width: 0 25px 25px 25px;
                                        border-style: solid;
                                    }
                                    &:after {
                                        content: '';
                                        bottom: -30px;
                                        width: 110px;
                                        position: absolute;
                                        border-color: $shadowColorB transparent transparent transparent;
                                        border-width: 25px 25px 0 25px;
                                        border-style: solid;
                                    }
                                }
                            }
                            .map-machine{
                                width: 100%;
                                min-height: 400px;
                                position: relative;
                                .machine-list{
                                    .machine-box{
                                        width: 40px;
                                        height: 24px;
                                        position: absolute;
                                        background: $machineColor;
                                        border-radius: 2px;
                                        box-shadow: 2px 2px 2px rgba(0,0,0,.1);
                                        display: flex;
                                        padding: 3px;
                                        box-sizing: border-box;
                                        .left-bar{
                                            width: 3px;
                                            background: #42d885;
                                            margin-right: 4px;
                                        }
                                        .right-bar{
                                            flex: 1;
                                            background: #42d885;
                                        }
                                        &.warning{
                                            background: $warningColor;
                                            .left-bar,.right-bar{
                                                background: #ee417a;
                                            }
                                        }
                                    }
                                    .desk{
                                        position: absolute;
                                        img{
                                            width: 25px;
                                            height: 25px;
                                            display: block;
                                        }
                                    }
                                }
                                .mb001{
                                    left: 80px;
                                    top: 85px;
                                    transform: rotate(-45deg);
                                }
                                .mb002{
                                    left: 130px;
                                    top: 66px;
                                }
                                .mb003{
                                    left: 180px;
                                    top: 66px;
                                }
                                .mb004{
                                    left: 230px;
                                    top: 66px;
                                }
                                .mb005{
                                    left: 300px;
                                    top: 153px;
                                    transform: rotate(-90deg);
                                }
                                .mb006{
                                    left: 300px;
                                    top: 220px;
                                    transform: rotate(-90deg);
                                }
                                .mb007{
                                    left: 277px;
                                    top: 287px;
                                    transform: rotate(-45deg);
                                }
                                .mb008{
                                    left: 215px;
                                    top: 310px;
                                }
                                .mb009{
                                    left: 150px;
                                    top: 310px;
                                }
                                .mb010{
                                    left: 82px;
                                    top: 290px;
                                    transform: rotate(45deg);
                                }
                                .mb011{
                                    left: 64px;
                                    top: 220px;
                                    transform: rotate(90deg);
                                }
                                .mb012{
                                    left: 64px;
                                    top: 153px;
                                    transform: rotate(90deg);
                                }
                                .dk001{
                                    left: 45px;
                                    top: 45px;
                                    transform: rotate(135deg);
                                }
                                .dk002{
                                    left: 138px;
                                    top: 15px;
                                    transform: rotate(180deg);
                                }
                                .dk003{
                                    left: 187px;
                                    top: 15px;
                                    transform: rotate(180deg);
                                }
                                .dk004{
                                    left: 237px;
                                    top: 15px;
                                    transform: rotate(180deg);
                                }
                                .dk005{
                                    left: 365px;
                                    top: 153px;
                                    transform: rotate(-90deg);
                                }
                                .dk006{
                                    left: 365px;
                                    top: 220px;
                                    transform: rotate(-90deg);
                                }
                                .dk007{
                                    left: 332px;
                                    top: 335px;
                                    transform: rotate(-45deg);
                                }
                                .dk008{
                                    left: 224px;
                                    top: 362px;
                                }
                                .dk009{
                                    left: 156px;
                                    top: 362px;

                                }
                                .dk010{
                                    left: 45px;
                                    top: 335px;
                                    transform: rotate(45deg);
                                }
                                .dk011{
                                    left: 10px;
                                    top: 220px;
                                    transform: rotate(90deg);
                                }
                                .dk012{
                                    left: 10px;
                                    top: 155px;
                                    transform: rotate(90deg);
                                }
                            }
                        }
                    }
                }
            }
        }
    }
    .msgbox{
        background-image: linear-gradient( 45deg, rgb(42,222,255) 0%, rgb(41,147,255) 100%);
        position: absolute;
        left: 30px;
        bottom: 26px;
        width: 120px;
        /*min-height: 54px;*/
        height: auto;
        z-index: 999;
        color: #e7e9ec;
        box-sizing: border-box;
        padding: 10px 4px;
        text-align: center;
        text-shadow: 1px 2px 2px rgba(0,0,0,.5);
        border-bottom-right-radius: 10px;
        border-top-left-radius: 10px;
        &:after{
            content: '';
            width: 35px;
            height: 1px;
            background: #fff;
            position: absolute;
            display: block;
            left: -26px;
            bottom: -13px;
            transform: rotate(-55deg);
        }
    }
    .wave{
        position: absolute;
        width: 50px;
        height: 50px;
        text-align: center;
        line-height: 50px;
        font-size: 28px;
        left: -15px;
        bottom: -26px;
    }
    .wave .circle {
        position: absolute;
        border-radius: 50%;
        opacity: 0;
    }
    .wave.ripple .circle {
        width: calc(100% - 6px); /* 减去边框的大小 */
        height: calc(100% - 6px);/* 减去边框的大小 */
        border: 3px solid #fff;
    }

    .wave.ripple .circle:first-child {
        animation: circle-opacity 2s infinite;
    }

    .wave.ripple .circle:nth-child(2) {
        animation: circle-opacity 2s infinite;
        animation-delay: .3s;
    }

    .wave.ripple .circle:nth-child(3) {
        animation: circle-opacity 2s infinite;
        animation-delay: .6s;
    }

    .wave.ripple.danger {
        color: red;
    }

    .wave.ripple.danger .circle {
        border-color: red;
    }

    .wave.ripple.warning {
        color: orange;
    }

    .wave.ripple.warning .circle {
        border-color: orange;
    }

    /* 波动效果 */
    .wave.solid .circle{
        width: 100%;
        height: 100%;
        background: #fff;
    }

    .wave.solid .circle:first-child {
        animation: circle-opacity 2s infinite;
    }

    .wave.solid.danger {
        color: red;
    }

    .wave.solid.danger .circle{
        background: red;
    }

    .wave.solid.warning {
        color: orange;
    }

    .wave.solid.warning .circle{
        background: orange;
    }

    @keyframes circle-opacity{
        from {
            opacity: 1;
            transform: scale(0);
        }
        to {
            opacity: 0;
            transform: scale(1);
        }
    }

</style>