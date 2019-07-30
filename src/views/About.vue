<template>
  <div class="about">
    <h2>Login</h2>
    <div>
      <div>{{msg}}</div>
      <!--            <div>-->
      <!--                <input type="text" id="account" placeholder="Account" v-model="user.account"/>-->
      <!--            </div>-->
      <!--            <div>-->
      <!--                <input type="password" id="password" placeholder="Password" v-model="user.password"/>-->
      <!--            </div>-->
      <div>
        <!--                <button @click="login">Login</button>-->
        <b-button>Login</b-button>
        <h2>123</h2>
      </div>
    </div>
  </div>
</template>

<script>
  import axiox from 'axios'

  export default {
    data() {
      return {
        msg: ''
      }
    },
    mounted() {
      axiox.get('/hello').then(response => {
        console.log(response);
        this.msg = response.data;
      })
    }
  }

</script>
