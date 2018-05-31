<template>
    <div class="box">
        <div class="header">
            <div class="header-left"><a href="#">logo</a></div>
            <ul class="header-right">
                <!-- <li class="header-nav" @mouseover="navIndex=0" @mouseout="navIndex=-1">
                    <span class="header-show" :style="{color:navIndex==0?'blue':''}">首页</span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==0"></span>
                    </transition>
                </li>
                <li class="header-nav" @mouseover="navIndex=1" @mouseout="navIndex=-1">
                    <span :style="{color:blue}">新闻中心</span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==1||true"></span>
                    </transition>
                </li>
                <li class="header-nav" @mouseover="navIndex=2" @mouseout="navIndex=-1">
                    <span :style="{color:navIndex==0?'blue':''}">
                        业务体系
                        <i></i>
                    </span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==2"></span>
                    </transition>
                </li>
                <li class="header-nav" @mouseover="navIndex=3" @mouseout="navIndex=-1">
                    <span :style="{color:navIndex==0?'blue':''}">关于我们</span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==3"></span>
                    </transition>
                </li>
                <li class="header-nav" @mouseover="navIndex=4" @mouseout="navIndex=-1">
                    <span :style="{color:navIndex==0?'blue':''}">招商合作</span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==4"></span>
                    </transition>
                </li>
                <li class="header-nav" @mouseover="navIndex=5" @mouseout="navIndex=-1">
                    <span :style="{color:navIndex==0?'blue':''}">欢迎加入</span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==5"></span>
                    </transition>
                </li> -->
                <li class="header-nav" v-for="(items,index) in nav" :key="index"
                @mouseover="navIndex=index" @mouseout="navIndex=-1">
                    <span class="header-show" :style="{color:navIndex==0?'blue':''}">
                        <span>{{items.text}}</span><i></i>
                    </span>
                    <transition name="fade">
                        <span class="header-underline" v-show="navIndex==index||items.status"></span>
                    </transition>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            navIndex:1,
            blue:'blue',
            nav:[
                {
                    text:'首页',
                    main:[],
                    status:false
                },
                {
                    text:'新闻中心',
                    main:[],
                    status:true
                },
                {
                    text:'业务体系',
                    main:[],
                    status:false
                },
                {
                    text:'关于我们',
                    main:[],
                    status:false
                },
                {
                    text:'招商合作',
                    main:[],
                    status:false
                },
                {
                    text:'欢迎加入',
                    main:[],
                    status:false
                }
            ]
        }
    }
}
</script>
<style lang="scss" scoped>
    .box{
        width: 100%;
        height: 75px;
        padding-top: 5px;
        box-sizing: content-box;
        border-bottom: 1px solid #e7e7e7;
        position: fixed;
        left: 0;
        top: 0;
        z-index: 9;

        .header {
            width: 1200px;
            height: 80px;
            margin: 0 auto;
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;

            .header-right {
                display: flex;
                flex-direction: row;

                .header-nav{
                    margin-left: 40px;
                    cursor: pointer;

                    .header-underline {
                        display: block;
                        width: 100%;
                        height: 3px;
                        margin-top: 6px;
                        background-color: blue;
                    }

                    .fade-leave-active {
                        transition: all 1s;
                    }

                    .fade-enter-active {
                        transition: all 0s;
                    }

                    .fade-leave-to {
                        width: 0;
                    }

                    .fade-enter {
                        width: 100%;
                    }
                }
            }
        }
    }
</style>
