<template>
  <v-container>
    <v-btn depressed @click="cambiarEstado()">
      Normal
    </v-btn>

    <SnackBar
      v-if="activeNotification"
      v-model="activeNotification"
      :isError="isError"
      :messages = "messages"
    />


  </v-container>
</template>

<script>
import SnackBar from './SnackBar.vue'
  export default {
    name: 'HelloWorld',
    data: () => ({
      activeNotification: false,
      isError: false,
      messages: "I am pretty sure you misunderstood the question.merlin was asking if Vue would generate native DOM events after input value is changed through the v-model binding."
    }),
    methods: {
      cambiarEstado(){
        this.activeNotification = true;
      }
    },
    components:{
      SnackBar
    }
  }
</script>
