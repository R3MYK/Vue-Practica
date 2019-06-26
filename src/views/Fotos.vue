<template>
  <div>
    <h1>Galeria de Fotografias:</h1>
    <!-- se pasan los parametros de router.js -->
    <router-link
      :to=" { name: 'fotos', params: {id : item} }"
      v-for="(item, index) of fotosArreglo"
      :key="index"
    >
      <button>foto {{item}}</button>
    </router-link>
    <Foto/>
    <button @click="home" >Home</button>
    <button @click="anterior" >Anterior</button>
    <button @click="siguiente" >Siguiente</button>
  </div>
</template>

<script>
import Foto from "@/components/Fotografia.vue";

export default {
  // name: "Fotos",
  components: {
    Foto
  },
  data() {
    return {
      fotosArreglo: [1, 2, 3]
    };
  },
  methods: {
    home() {
      this.$router.push("/"); //Redirecciona al Home
    },
    anterior(){
      this.$router.go(-1)//Historial
    },
    siguiente(){
      this.$router.go(1)//Historial
    }
  }
};
</script>