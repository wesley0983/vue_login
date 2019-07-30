<template>
    <div class="login">
        <h2>Login</h2>
        <div>
            <div>{{msg}}</div>
            <div>
                <b-form @submit="onSubmit">
                    <b-form-input v-model="username" placeholder="請輸入帳號"></b-form-input>
                    <b-button @click="onSubmit">submit</b-button>
                </b-form>
            </div>

        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    import qs from 'qs'

    export default {
        data() {
            return {
                username: '',
                msg: ''
            }
        },
        methods: {

            onSubmit() { // post x-www-form-urlencoded 送出 需要用到 qs套件配合
                axios.post('/helloword', qs.stringify({
                    'username':'123'
                })).then(respose => {
                    console.log(respose.data);
                })
            }
            /*
            onSubmit() { //post json送出
                let username = this.username;
                let password = "123";
                axios.post('/user',{
                    username,password
                }).then(respose => {
                    console.log(respose.data);
                })
            }*/
        },
        // mounted() {
        //     axiox.get('/hello').then(response => {
        //         console.log(response);
        //         this.msg = response.data;
        //     })
        // }
    }
</script>
