<template>
  <div id="appSignup">
    <h2>Registro</h2>
    <form>
      <div>
        <label for="username">Usuario:</label>
        <input type="text" id="userNameSignup" v-model="username" />
      </div>
      <div>
        <label for="firstName">Primer nombre:</label>
        <input type="text" id="firstName" v-model="firstName" />
      </div>
      <div>
        <label for="secondName">Segundo nombre:</label>
        <input type="text" id="secondName" v-model="secondName" />
      </div>
      <div>
        <label for="lastName">Apellidos:</label>
        <input type="text" id="lastName" v-model="lastName" />
      </div>
      <div>
        <label for="phone">Celular:</label>
        <input type="phone" id="phone" v-model="phone" />
      </div>
      <div>
        <label for="email">Correo:</label>
        <input type="email" id="emailSignup" v-model="email" />
      </div>
      <div>
        <label for="password">Contraseña:</label>
        <input type="password" id="passwordSignup" v-model="password" />
      </div>
      <div>
        <label for="repeatPassword">Repetir contraseña:</label>
        <input type="password" id="Repeatpassword" v-model="repeatPassword" />
      </div>
      <button @click.stop="Registro" type="button">Registrarse</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const email = ref("");
const username = ref("");
const password = ref("");
const firstName = ref("");
const secondName = ref("");
const lastName = ref("");
const phone = ref("");
const repeatPassword = ref("");

function Registro() {
  const validEmailRegex = /^\w+([.-_+]?\w+)*@\w+([.-]?\w+)*(\.\w{2,10})+$/;
  const regexpPassword =
    /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[$@$!%*?&])[A-Za-z\d$@$!%*?&]{8,15}/;

  console.log(validEmailRegex.test(email.value));
  console.log(regexpPassword.test(password.value));
  console.log(password.value === repeatPassword.value);
  if (
    validEmailRegex.test(email.value)
  ) {
    alert("Registro exitoso");
    return true;
  }
    alert(" incorrectos");
    return false;
  }

  if (
    regexpPassword.test(password.value) &&
    password.value === repeatPassword.value
  ) {
    alert("Registro exitoso");
    return true;
  } else {
    alert("Datos incorrectos");
    return false;
  }
}
</script>
