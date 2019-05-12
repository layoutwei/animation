<template>
    <div class="menu">
        <ul>
            <transition-group name="slide-fade">
                <li
                    v-for="item, key in guids"
                    :key="key"
                    :class="{active : active == key}"
                    :title="item.describe" :style="{
                        animationDelay: key * .02 + 's'
                    }" @click="active=key"
                    v-if="item.show">
                        {{item.name}}
                    </li>
            </transition-group>
        </ul>
    </div>
</template>
<script>
    export default {
        data () {
            console.log(this)
            return {
                active: -1,
                guids: [
                    {
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },
                    {
                        name: '渐变显示',
                        className: '',
                        show: false,
                        describe: ''
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },{
                        name: '测边进入',
                        className: '',
                        show: false,
                        describe: '侧边进入，渐变'
                    },
                ]
            }
        }
    }
</script>
<style lang="less" scope="scope">
    .slide-fade-enter-active {
        animation-name: slide-left;
        animation-duration: .3s;
        animation-delat: 1.5s;
    }
    .active (@color: #333) {
        text-decoration: underline;
        color:cornflowerblue;
        animation: slide-hover .1s;
        animation-fill-mode: forwards;
        color: @color;
    }
    .menu {
        position: fixed;
        width: 130px;
        height: 100%;
        left: 0;
        top: 0;
        border-right: 1px solid #eee;
        background-color: #eeefff;
        ul {
            height: 100%;
            width: 100%;
            margin: 0;
            padding: 0;
            overflow-x: hidden;
            overflow-y: auto;
            li {
                list-style: none;
                margin: 0;
                text-indent: 10px;
                font-size: 14x;
                height: 30px;
                width: 100%;
                line-height: 30px;
                cursor: pointer;
                user-select: none;
                overflow: hidden;
                text-overflow: ellipsis;
                white-space: nowrap;
                &:hover {
                    
                    
                }
            };
        }
    }
    @keyframes slide-left {
        from {
            margin-left: -150px;
        }
        to {
            margin-left: 0;
        }
    }
    @keyframes slide-hover {
        from {
            width: 150px;
            transform: translate(0px, 0);
            margin-left: 0;
        }
        to {
            width: 155px;
            transform: translate(-5px, 0);
            margin-left: 0;
        }
    }
</style>