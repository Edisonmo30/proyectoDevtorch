<template>
  <div id="app">
    <h2>Login</h2>
    <form>
      <div>
        <label for="username">Usuario:</label>
        <input type="text" id="username" v-model="username">
      </div>
      <div>
        <label for="password">Contraseña:</label>
        <input type="password" id="password" v-model="password">
      </div>
      <button @click.stop="login" type="button" >Iniciar sesión</button> 
    </form>
  </div>

</template>

<script setup>
    const username = ref('')
    const password = ref('')

    
    function login(){
        const validEmailRegex = /^\w+([.-_+]?\w+)*@\w+([.-]?\w+)*(\.\w{2,10})+$/
        const regexp_password = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[$@$!%*?&])[A-Za-z\d$@$!%*?&]{8,15}/;
        if(validEmailRegex.test(username.value) && regexp_password.test(password.value)){
          alert('Bienvenido')
          return true
        }else{
          alert('Datos incorrectos')
            return false 
        }
    }
</script>

<style>

</style>

