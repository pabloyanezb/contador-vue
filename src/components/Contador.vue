<template>
  <div>
    <p v-if="!$store.state.hovered" class="no-visible">Este texto es invisible</p>
    <p v-if="$store.state.count!=1 && $store.state.hovered">Has clickeado {{$store.state.count}} veces</p>
    <p v-if="$store.state.count==1 && $store.state.hovered">Has clickeado {{$store.state.count}} vez</p>
    <button @click="clic()" @mouseover="hover()">click!</button>
  </div>
</template>

<script>
export default {
  name: "Contador",
  methods: {
    clic() {
      this.$store.commit('increment');
      localStorage.count = this.$store.state.count;
    },
    hover() {
      console.log("mouseover");
      this.$store.commit('hover_true');
    }
  },
  mounted() {
    if (localStorage.count) {
      this.$store.state.count = localStorage.count;
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