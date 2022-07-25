<template>
  <h2>{{tituloComputed}}</h2>
  <p>{{counter}} <sup>2</sup> = {{ cuadrado }}</p>
  <input class="button" @click="aumentar" type="button" value="+">
  <input class="button" @click="disminuir" type="button" value="-">
</template>

<script>
export default {
    name: 'Counter',
    props: {
      titulo: String,
      start: {
        type: Number,
        required: true,
        default: 1
      }
    },
    data(){
      return {
        counter: this.start
      }
    },
    methods: {
      aumentar(){
        this.counter = this.counter+1;
      },
      disminuir(){
        this.counter = this.counter-1;
      }
    },
    computed: {
      cuadrado(){
        return this.counter*this.counter
      },
      tituloComputed(){
        return this.titulo || "counter"
      }
    },
}
</script>

<style>
  h2 {
    text-transform: uppercase;
  }
  .button {
    background: green;
    color: whitesmoke;
    cursor: pointer;
    margin-left: 5px;
  }

  .button:hover {
    background: blue;
  }
</style>