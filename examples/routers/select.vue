<template>
    <div class="mgl">
        <Select v-model="model1" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>

        <Select v-model="model2" multiple placement="top" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
        <Select v-model="model2" multiple placement="bottom" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
        <Select v-model="model2" multiple placement="top-start" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
        <Select v-model="model2" multiple placement="bottom-start" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
        <Select v-model="model2" multiple transfer placement="left-start" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>

        <Select v-model="model2" multiple clearable filterable placement="left" style="height:200px">
            <Option v-for="item in cityList" :value="item.value" :key="item.value">{{ item.label }}</Option>
        </Select>
        <br>
        <Input v-model="value11">
            <span slot="prepend">http://</span>
            <span slot="append">.com</span>
        </Input>
        <br>
        <Input v-model="value12">
            <Select v-model="select1" slot="prepend" style="height: 80px">
                <Option value="http">http://</Option>
                <Option value="https">https://</Option>
            </Select>
            <Select v-model="select2" slot="append" style="height: 70px">
                <Option value="com">.com</Option>
                <Option value="org">.org</Option>
                <Option value="io">.io</Option>
            </Select>
        </Input>
        <br>
        <Input v-model="value13">
            <Select v-model="select3" slot="prepend" style="height: 80px">
                <Option value="day">Day</Option>
                <Option value="month">Month</Option>
            </Select>
            <Button slot="append" icon="ios-search"></Button>
        </Input>
    </div>
</template>
<script>
    export default {
        data () {
            return {
                value11: '',
                value12: '',
                value13: '',
                select1: 'http',
                select2: 'com',
                select3: 'day',
                cityList: [
                    {
                        value: 'New York',
                        label: 'New York'
                    },
                    {
                        value: 'London',
                        label: 'London'
                    },
                    {
                        value: 'Sydney',
                        label: 'Sydney'
                    },
                    {
                        value: 'Ottawa',
                        label: 'Ottawa'
                    },
                    {
                        value: 'Paris',
                        label: 'Paris'
                    },
                    {
                        value: 'Canberra',
                        label: 'Canberra'
                    }
                ],
                model1: '',
                model2: []
            }
        }
    }
</script>
