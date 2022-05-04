<template>
  <h3 style="text-align: left;">Lista towarów</h3>
  <table>
    <tr>
      <th>Nazwa towaru</th>
      <th>Cena</th>
    </tr>
    <tr v-for="d of data" :key="d.id">
      <th>{{ d.name }}</th>
      <th>{{ d.price }}</th>
      <th><button @click="d.inCart++">+</button></th>
      <th><button @click="d.inCart--">-</button></th>
    </tr>
  </table>
  <hr>
  <h3 style="text-align: left;">Koszyk</h3>
  <table>
    <tr>
      <th>Nazwa towaru</th>
      <th>W koszyku</th>
    </tr>
    <tr v-for="d of data" :key="d.id">
      <th v-if="d.inCart > 0">{{ d.name }}</th>
      <th v-if="d.inCart > 0">{{ d.inCart }}</th>
      <th v-if="d.inCart > 0"> {{ d.inCart * d.price }}</th>
    </tr>
  </table>
  <h3 style="text-align: left;">{{x}}</h3>

</template>

<script>
  import data from './data.js'
  import { ref, reactive } from 'vue'
  var x = 0
  console.log(data._rawValue.length)
  for (let i = 0; i < data._rawValue.length; i++) {
    x++
    console.log(x)
  }
  export default {
    data() {
      
      return {
        data,
        x,
      }
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
