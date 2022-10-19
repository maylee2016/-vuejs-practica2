<template>
  <div class="container">

    <div class="row">
      <h3>{{ producto.nombre }}</h3>
    </div>
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4 ">
        <img :src="producto.imagen" :alt="producto.nombre" width="100%">
      </div>
      <div class="col-12 col-sm-6  col-md-8">
        <h6>S6S Mini GPS Drones 150g Drone 4K Profesional HD Dual Camera 5G WIFI FPV Brushless Folding Quadcopter RC
          Dron Helicopter Toys</h6>
        <div class="p-3 mb-2 text-white" :style="configuracionPagina.precioEstilos">
          Precio: {{ producto.precio }} BOB
        </div>
        <h5>Color</h5>
        <div>
          <div v-for="(color, index) in producto.colores " v-bind:key="index" class="color-box clic"
               :style="`background:${color}`"></div>
        </div>
        <h5>Cantidad</h5>
        <div class="quantity">
          <button @click="disminuir">-</button>
          <div>{{ contador }}</div>
          <button @click="aumentar">+</button>
        </div>
        <div class="buy-box">
          <button type="button" class="btn btn-primary" :disabled="changeStyle" @click="comprar">Comprar</button>
        </div>

      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  name: 'MiProduct',
  data() {
    return {
      producto: [],
      configuracionPagina: [],
      contador: 1
    }
  },
  mounted() {
    axios.get('http://localhost:3000/Producto')
        .then(response => this.producto = response.data)
        .catch(error => console.log(error))
    axios.get('http://localhost:3000/configuracionPagina')
        .then(response => this.configuracionPagina = response.data)
        .catch(error => console.log(error))

  },
  methods: {
    aumentar() {
      this.contador++
    },
    disminuir() {
      if (this.contador > 0) {
        this.contador--
      }
    },
    comprar() {
    },
  },
  computed: {}
}
</script>