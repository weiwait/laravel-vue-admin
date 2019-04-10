<template>
    <div class="EditModel">
        <component v-for="attribute in attributes" v-bind:ref="attribute.name" v-bind:prop-data="attribute.data" v-bind:is="useComponent(attribute.component)"></component>
        <el-button v-on:click="test()">test</el-button>
    </div>
</template>

<script>
    import AdminComponent from '../ShowComponents';

    export default {
        props: {
        },
        data() {
            return {
                attributes: [
                    {component: 'About', name: 'hello', data: {value: 'hello'}},
                    {component: 'About', name: 'world', data: {value: 'world'}}
                ],
                form: {
                    hello: ''
                }
            }
        },
        updated() {
            console.log(this.form)
        },
        methods: {
            test: function () {
                this.attributes.forEach((item, index) => {
                    console.log(this.$refs[item.name][0].formData)
                });
            },
            useComponent: function (name) {
                return AdminComponent[name];
            }
        }
    };
</script>
