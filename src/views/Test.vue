<template>
    <div class="about">
        <el-input placeholder="请输入内容" v-model="formData" clearable ></el-input>
    </div>
</template>

<script>
    export default {
        props: [
            'prop-data'
        ],
        data() {
            return {
                formData: this.$props.propData.value
            }
        },
        updated() {
            this.$parent.form.hello = this.formData
        }
    }
</script>
