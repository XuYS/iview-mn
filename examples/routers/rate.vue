<template>
    <div>
        <Rate allow-half v-model="valueHalf" />
        <Rate show-text allow-half v-model="valueCustomText">
            <span style="color: #f5a623">{{ valueCustomText }}</span>
        </Rate>
        <Rate v-model="value5" icon="ios-heart" />
    </div>
</template>
<script>
export default {
    data() {
        return {
            valueHalf: 2.5,
            valueCustomText: 3.8,
            value5: 3
        };
    }
};
</script>