<template>
  <div id="app">
      <v-header id="header"></v-header>
    <div class="body">
      <div v-for="(data,index) in main_data" style="text-align: center">
        <p class="time">{{data.time}}</p>
        <v-list :datas="datas[index]" :main="data" ></v-list>
      </div>
    </div>
    <v-footer></v-footer>

  </div>
</template>

<script>
  const axios = require('axios');
import header from './components/header'
import list from './components/list'
import footer from './components/footer'

export default {
  name: 'App',
  components: {
    "v-header": header,
    "v-list": list,
    "v-footer":footer,

  },
  data() {
    return {
      main_data:'',
      datas:'',
      scroll: '',
    }
  },
  beforeCreate() {
    this.$axios.post("/apis/api/data_test.php",{
    }).then(data=>{
      this.main_data=data.data[0];
      this.datas=data.data[1];
    });
  },
  mounted: function () {

    window.addEventListener('scroll', this.handleScroll);
  },

  methods: {
    handleScroll: () => {
      const height = document.getElementById('header').offsetHeight;
      this.scroll = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
      const opacity = this.scroll / height;
      if (opacity <= 1) {
        if (opacity <= 0.45) {
          document.getElementById("scroll").setAttribute('style', 'opacity:' + (1 - opacity).toString());
          document.getElementById("fix").setAttribute('style', 'opacity:' + opacity.toString());
        } else {
          document.getElementById("scroll").setAttribute('style', 'opacity:0');
          document.getElementById("fix").setAttribute('style', 'opacity:' + opacity.toString());


        }
      } else {
        document.getElementById("scroll").setAttribute('style', 'opacity:0');
        document.getElementById("fix").setAttribute('style', 'opacity:1');
      }
    }
  },
}





</script>


<style>

*{
  margin: 0;
}
.time{
  margin-top: 10px;
  color: #d4d4d4;
}
</style>
