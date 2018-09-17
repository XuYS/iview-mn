<template>
    <div style="margin: 100px;" class="color">
        {{ color1 }}
        <ColorPicker v-model="color1" />
        <ColorPicker v-model="color2" :editable="false"/>
    </div>
</template>
<script>
    export default {
        data () {
            return {
                color1: '#19be6b',
                color2: ''
            };
        }
    };
</script>
<style lang="less" scoped>
    .color{
        writing-mode: vertical-lr;
    }
</style>

