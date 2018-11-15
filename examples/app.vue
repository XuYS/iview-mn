<style lang="less">
    @import "../src/styles/index.less";
    .mgl{
        writing-mode: vertical-lr
    }
</style>
<style lang="less" scoped>
nav {
    margin-bottom: 40px;

    ul { display: flex; flex-wrap: wrap; }
    li { display: inline-block; }
    li + li { border-left: solid 1px #bbb; padding-left: 10px; margin-left: 10px; }
}
.container{ padding: 10px 40px 0; }
.v-link-active { color: #bbb; }
</style>
<template>
    <div class="container">
        <nav>
            <ul>
                <li v-for="(item,index) in moduleList" :key="index" >
                    <router-link :to="item.to">
                        <span :style="item.accomplish?'color:white;background-color:green;':''">{{item.name}}</span>
                    </router-link>
                </li>
            </ul>
        </nav>
        <div class="ui-components mgl" style="height:80%;">
            <router-view></router-view>
        </div>
    </div>
</template>
<script>
    module.exports = {
        data: function() {
            return {
                moduleList:[
                    {name:'Split',to:'/split',accomplish:false,},
                    {name:'Layout',to:'/layout',accomplish:false,},
                    {name:'Affix',to:'/affix',accomplish:false,},
                    {name:'Anchor',to:'/anchor',accomplish:false,},
                    {name:'Grid',to:'/grid',accomplish:false,},
                    {name:'Button',to:'/button',accomplish:false,},
                    {name:'Input',to:'/input',accomplish:true,},
                    {name:'Radio',to:'/radio',accomplish:true,},
                    {name:'Checkbox',to:'/checkbox',accomplish:true,},
                    {name:'Steps',to:'/steps',accomplish:false,},
                    {name:'Timeline',to:'/timeline',accomplish:false,},
                    {name:'Switch',to:'/switch',accomplish:false,},
                    {name:'Alert',to:'/alert',accomplish:true,},
                    {name:'Badge',to:'/badge',accomplish:true,},
                    {name:'Tag',to:'/tag',accomplish:false,},
                    {name:'InputNumber',to:'/input-number',accomplish:true,},
                    {name:'Progress',to:'/progress',accomplish:false,},
                    {name:'Upload',to:'/upload',accomplish:false,},
                    {name:'Collapse',to:'/collapse',accomplish:false,},
                    {name:'Carousel',to:'/carousel',accomplish:false,},
                    {name:'Card',to:'/card',accomplish:true,},
                    {name:'Tree',to:'/tree',accomplish:true,},
                    {name:'Rate',to:'/rate',accomplish:true,},
                    {name:'Circle',to:'/circle',accomplish:false,},
                    {name:'Tabs',to:'/tabs',accomplish:true,},
                    {name:'Tooltip',to:'/tooltip',accomplish:true,},
                    {name:'Poptip',to:'/poptip',accomplish:true,},
                    {name:'Slider',to:'/slider',accomplish:false,},
                    {name:'Dropdown',to:'/dropdown',accomplish:false,},
                    {name:'Breadcrumb',to:'/breadcrumb',accomplish:true,},
                    {name:'Menu',to:'/menu',accomplish:true,},
                    {name:'Spin',to:'/spin',accomplish:true,},
                    {name:'Cascader',to:'/cascader',accomplish:false,},
                    {name:'Select',to:'/select',accomplish:true,},
                    {name:'Backtop',to:'/back-top',accomplish:false,},
                    {name:'Page',to:'/page',accomplish:true,},
                    {name:'Transfer',to:'/transfer',accomplish:true,},
                    {name:'DatePicker',to:'/date',accomplish:true,},
                    {name:'Form',to:'/form',accomplish:true,},
                    {name:'Table',to:'/table',accomplish:true,},
                    {name:'LoadingBar',to:'/loading-bar',accomplish:true,},
                    {name:'Modal',to:'/modal',accomplish:true,},
                    {name:'Message',to:'/message',accomplish:true,},
                    {name:'Notice',to:'/notice',accomplish:true,},
                    {name:'Avatar',to:'/avatar',accomplish:true,},
                    {name:'ColorPicker',to:'/color-picker',accomplish:true,},
                    {name:'AutoComplete',to:'/auto-complete',accomplish:true,},
                    {name:'Scroll',to:'/scroll',accomplish:false,},
                    {name:'Divider',to:'/divider',accomplish:true,},
                    {name:'Time',to:'/time',accomplish:true,},
                    {name:'Cell',to:'/cell',accomplish:true,},
                    {name:'Drawer',to:'/drawer',accomplish:true,},
                ]
            }
        },
        mounted: function() {

        },
        beforeDestroy: function() {

        },
        methods: {

        }
    }
</script>
