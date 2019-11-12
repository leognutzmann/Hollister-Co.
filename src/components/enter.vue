<template>
  <div class="row">
    <div class="bg-white size shadow rounded">
        <div class="form-group mx-3 my-5">
          <label for="username" class="text-dark">Username</label>
          <input type="text" class="form-control" id="username" placeholder="Username" v-model="username">
        </div>
        <div class="form-group mx-3 ">
          <label for="password" class="text-dark">Password</label>
          <input type="password" class="form-control" id="password" placeholder="Password" v-model="password">
        </div>
        <div class="container">
          <button type="button" @click.prevent="checkLogin" :disabled="!(username && password)" class="btn btn-primary btn-lg btn-block mt-5">Login</button>
        </div>
        <div class="container">
          <div class="row mt-3">
            <div class="col-5 offset-1">
            <a href="#" class="text-secondary text-decoration-none">Esqueceu a senha?</a>
          </div>
          <div class="col-5 offset-1">
            <a href="#" class="text-secondary text-decoration-none">Novo? Criar conta</a>
          </div>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'enter',
  methods: {
    checkLogin: function(){
      if(this.password == '123')
        this.$router.push('home');
      else{
        this.$bvToast.toast('Usuário e/ou senha incorretos, tente novamente', {
          title: 'Senha incorreta',
          autoHideDelay: 5000
        })
      }
    }
  },
  data: function(){
    return{
      username: '',
      password: ''
    }
  }
}
</script>

<style scoped>
.size{
  height: 26rem;
}
</style>
