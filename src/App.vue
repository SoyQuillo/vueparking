<script setup>

let objeto = {
  moto: 500,
  carro:1000,
  pesado: 2000,
}

let listParqueadero = [{
tipo: 'moto',
tiempo: 15,
stay: true,
},
{
  tipo: 'carro',
  tiempo: 30,
  stay: false,
},
{
  tipo: 'pesado',
  tiempo: 15,
  stay: true,
}]

let total = 0;

function general (tiempo, tipo){

total = (objeto[tipo] * tiempo)/15;

return total;

}
</script>

<template>
  
<ul>
  <h1>LISTA PARQUEADERO</h1>
  <span v-for="(obj, index) in listParqueadero" :key="index">
  <li>{{ general(obj.tiempo, obj.tipo) }}</li>
  </span>
</ul>

<span>LISTA DE CARROS QUE AUN ESTAN</span>
<ul>
  <span v-for="(objeto, index) in listParqueadero" :key="index">
  <li v-if="objeto.stay">
    {{ objeto.tipo }}
  </li>
  </span>
</ul>


<span> LISTA DE CARROS QUE YA NO ESTAN</span>
<ul>
  <span v-for="(objeto, index) in listParqueadero" :key="index">
    <li v-if="objeto.stay == false">
    {{ objeto.tipo }}
    </li>
  </span>
</ul>


    
</template>

<style scoped>

</style>
