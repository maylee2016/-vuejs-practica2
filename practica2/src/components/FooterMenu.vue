<template>
    <footer :style="{background: configuracionPagina.footerColor}"></footer>
</template>


<script>

import axios from "axios";

export default {
  name: "NavbarMenu",
  data() {
    return {
      configuracionPagina: []
    }
  },
  mounted() {
    axios.get('http://localhost:3000/configuracionPagina')
        .then(response => this.configuracionPagina = response.data)
        .catch(error => console.log(error))
  }
}
</script>