<template>
    <div class="login">
        <h2>Login</h2>
        <div>
            <div>{{msg}}</div>
            <div>
<!--                <b-form @submit="onSubmit">-->
                    <b-form-input v-model="username" placeholder="請輸入帳號"></b-form-input>
                    <b-button @click="onSubmit">submit</b-button>
<!--                </b-form>-->
            </div>

        </div>
    </div>
</template>

<script>
    import axiox from 'axios'

    export default {
        data() {
            return {
                username:'',
                msg: ''
            }
        },
        methods: {
            onSubmit() {
                console.log(this.username);
                axios.post('/helloword',{
                    'username':this.username
                }).then(respose => {
                    console.log(respose.data)
                })
            }
        },
        // mounted() {
        //     axiox.get('/hello').then(response => {
        //         console.log(response);
        //         this.msg = response.data;
        //     })
        // }
    }

</script>
