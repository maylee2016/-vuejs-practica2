<template>
  <NavbarMenu/>
  <main>
    <MiProduct/>
    <ProductsList/>
  </main>
  <FooterMenu/>
</template>

<script>

import NavbarMenu from "./components/NavbarMenu.vue";
import MiProduct from "./components/MiProduct.vue";
import ProductsList from "./components/ProductsList.vue";
import FooterMenu from "./components/FooterMenu.vue";

export default {
  name: "App",
  components: {
    NavbarMenu,
    MiProduct,
    ProductsList,
    FooterMenu
  },
};
</script>

<style>
.color-box {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin: 7px;
  display: inline-block;
}

.clic {
  cursor: pointer;
}

.quantity button {
  border-radius: 50%;
  display: inline-block;
  width: 30px;
}

.quantity div {
  text-align: center;
  min-width: 30px;
  display: inline-block;
  font-weight: bold;
}

.buy-box {
  margin: 20px;
}

footer {

  text-align: center;
  padding: 30px 10px;
  margin-top: 50px;
  min-height: 100px;
}

.container {
  margin-top: 50px;
}

.producto-relacionado-precio {
  background: orangered;
  color: white;
  text-align: center;
  padding: 10px;
}
</style>
