<template>
  <template v-if="autenticado">
    <router-view />
  </template>
  <template v-else>
    <div>
      <h1>hola mundo</h1>
    </div>
  </template>
  <button @click="mostrarApp">Mostrar app</button>
</template>

<script>
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'App',
  data() {
    return {
      autenticado: false,
      count:0
    }
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
  methods: {
    mostrarApp() {
      this.autenticado=!this.autenticado;
      this.count++;
      console.log(`The count is ${this.count}.`)

    }
  },


  mounted() {
    console.log(`The initial count is ${this.count}.`)
  }
})
</script>
