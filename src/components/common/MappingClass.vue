<template>
    <el-select
        v-model="cls.dynamic"
        class="w3 wp mr10"
        placeholder="点击选择">
        <el-option v-for="(item, index) in dynamicTypes" :key="index" :label="`${item.value}`" :value="item.value">
            <span>{{item.name}}</span>
        </el-option>
    </el-select>
</template>

<script>
export default {
    name: "mappingClass",
    data() {
        return {
            cls: {},
            dynamicTypes: [
                {name: "true (默认值，动态添加字段)", value: "true"},
                {name: "false (忽略新字段)", value: "false"},
                {name: "strict (陌生字段抛出异常)", value: "strict"},
            ],
        };
    },
    props: {
        mapClass: {
            type: Object,
            required: true
        },
    },
    created() {

    },
    mounted() {
        this.cls = this.mapClass;
    },
    computed: {

    },
    methods: {

    }
};
</script>

<style scoped>

.w1 {
    width: 180px;
}
.w2 {
    width: 85px !important;
}
.w3 {
    width: 120px;
}
.wp {
    margin-right: 8px;
    display: inline-block;
}
.title {
    font-weight: bold;
}
</style>