<template>
  <div>
    <p v-if="!hovered" class="no-visible">Este texto es invisible</p>
    <p v-if="contador!=1 && hovered">Has clickeado {{contador}} veces</p>
    <p v-if="contador==1 && hovered">Has clickeado {{contador}} vez</p>
    <button @click="clic()" @mouseover="hover()">click!</button>
  </div>
</template>

<script>
export default {
  name: "Contador",
  data() {
    return {
      contador: 0,
      hovered: false
    };
  },
  methods: {
    clic() {
      this.contador++;
      localStorage.contador = this.contador;
    },
    hover() {
      console.log("mouseover");
      this.hovered = true;
    }
  },
  mounted() {
    if (localStorage.contador) {
      this.contador = localStorage.contador;
    }
  }
};
</script>

<style scoped>
.no-visible {
  color: transparent;
}
button {
  padding: 10px 35px;
  background-color: #f8e9a1;
  color: #242d52;
  border: 0;
  border-radius: 5px;
  font-size: 20px;
  font-weight: 900;
  font-family: "Knewave", cursive;
}
button:hover {
  box-shadow: 0 0 3pt 0pt #fef9c7;
}
button:focus {
  outline: none;
}
</style>