<template>
    <div :class="prefixCls + '-operation'" :style="{height:height}">
        <div :class="prefixCls + '-operation-top'">
            <i-button type="primary" size="small" :disabled="!rightActive" @click.native="moveToLeft">
                <Icon type="ios-arrow-back"></Icon> <span>{{ operations[0] }}</span>
            </i-button>
        </div>
        <div :class="prefixCls + '-operation-bottom'">
            <i-button type="primary" size="small" :disabled="!leftActive" @click.native="moveToRight">
                <span>{{ operations[1] }}</span> <Icon type="ios-arrow-forward"></Icon>
            </i-button>
        </div>
    </div>
</template>
<script>
    import iButton from '../button/button.vue';
    import Icon from '../icon/icon.vue';

    export default {
        name: 'Operation',
        components: { iButton, Icon },
        props: {
            prefixCls: String,
            operations: Array,
            leftActive: Boolean,
            rightActive: Boolean,
            height: String
        },
        methods: {
            moveToLeft () {
                this.$parent.moveTo('left');
            },
            moveToRight () {
                this.$parent.moveTo('right');
            }
        }
    };
</script>
