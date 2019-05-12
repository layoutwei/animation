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
                    }" @click="itemClick(key, item.componentName)">
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
                        componentName: 'fadeSlide',
                        describe: '侧边进入，渐变'
                    },
                    {
                        name: '渐变透明',
                        className: '',
                        componentName: 'fadeIn',
                        describe: '渐变透明'
                    }
                ]
            }
        },
        methods: {
            itemClick (key, cname) {
                this.active = key
                this.$emit('animationChange', cname)
            }
        }
    }
</script>
<style lang="less" scope="scope">
    .active (@color: cornflowerblue) {
        width: 155px;
        background: linear-gradient(#fff, #ccc);
        text-decoration: underline;
        color: @color;
        transform: translate(-5px, 0);
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
            .active {
                .active(rgb(31, 12, 204))
            };
            li {
                list-style: none;
                margin: 0;
                text-indent: 10px;
                font-size: 13x;
                height: 30px;
                width: 100%;
                line-height: 30px;
                cursor: pointer;
                user-select: none;
                overflow: hidden;
                animation: slide-left;
                animation-duration: .3s;
                animation-fill-mode: forwards;
                text-overflow: ellipsis;
                white-space: nowrap;
                margin-left: 150px;
                &:hover {
                    .active()
                }
            };
        }
    }
    @keyframes slide-hover {
        from {
            margin-left: 0
        }
        to {
            margin-left: 0;
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
    
</style>