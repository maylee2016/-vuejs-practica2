<template>
  <div class="container ">

    <div class="row">
      <h4>Productos relacionados</h4>
    </div>
    <div class="row">
      <div class="col" v-for="producto in products" :key="producto">
        <div class="card" style="width: 18rem;">
          <div class="card-body">
            <h5 class="card-title">{{ producto.nombre }}</h5>
            <img :src="producto.imagen"
                 :alt="producto.nombre" width="200">
            <p class="card-text">{{ producto.descripcion }}</p>
            <div class="producto-relacionado-precio">Precio:{{ producto.precio }} BOB</div>
            <div>
              <div>
                <div v-for="color in producto.colores" :key="color" class="color-box"
                     :style="{background: color}"></div>
                <!-- <div class="color-box" style="background: blue"></div>
                <div class="color-box" style="background: black"></div> -->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'

export default {
  name: 'ProductsList',
  data() {
    return {
      products: [],
      contador: 1,
      deshabilitado: false
    }
  },
  mounted() {
    axios.get('http://localhost:3000/Productos')
        .then(response => this.products = response.data)
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
  },
  computed: {
    changeStyle() {
      return this.deshabilitado < 1
    }
  }
}
</script>