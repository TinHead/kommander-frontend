<template>
  <la-cartesian :bound="[0, n => n + 300]" :data="values">
    <la-line dot curve prop="ext"></la-line>
    <la-line dot curve prop="bed"></la-line>
    <la-x-axis prop="name"></la-x-axis>
    <la-y-axis prop="name"></la-y-axis>
    <la-tooltip></la-tooltip>
  </la-cartesian>
</template>

<script>
import { Cartesian, Line } from 'laue'
import axios from 'axios'

export default {
  components: {
    LaCartesian: Cartesian,
    LaLine: Line
  },
mounted(){
    axios
    .get("http://127.0.0.1:8090/ping")
    .then(function(response){
        console.log(response);
    })
},
    
    data: () => ({
    values: [
      { name: '5', ext: 40, bed: 24 },
      { name: '10', ext: 50, bed: 40 },
      { name: '15', ext: 60, bed: 100 }
    ]
  })
};
</script>
