<script>
export default {
  data(){
    return{
      datasensor: "60",
      datasensor2:"80",
    };
  },
  created(){
    //this.getData()
  },
  methods:{
    async getData() {
      const data = await  fetch("http://localhost/sensor1")
      const datajson = await data.json()
      this.datasensor = datajson.sensor1
    },
  },
};
</script>

<template>
  <div>Hello World {{ datasensor }}
    <button @click="getData" class="bg-red-400 p-2 rounded-3xl">Ambil Data</button>
  </div>
</template>

