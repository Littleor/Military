<template>
    <div class="contain">
      <div id="main" class="main" @click='jump(main.url)'>
        <img :src="main.img">
        <p>{{main.title}}</p>
      </div>
      <div class="list" v-for="data in datas" @click='jump(data.url)'>
        <p>{{data.title}}</p>
        <img :src="data.img">
        <div></div>
      </div>
    </div>

</template>

<script>
    export default {
        name: "list",
        data:{

        },
      props:{
        main:Object,
        datas:Array,
      },
      methods:{
          jump:function (url) {
            window.location.href=url;
          }
      }
    }
</script>

<style scoped>
  .contain{
    margin: 10px auto 10px auto;
    width:95vw ;
    -moz-box-shadow:2px 2px 3px #333333;
    -webkit-box-shadow:2px 2px 3px #333333;
    box-shadow:2px 2px 3px #333333;
  }
  .main{
    width:95vw ;
    height:40.4255vw;
    position: relative;
    text-align: center;
    -moz-box-shadow:2px 2px 3px #333333;
    -webkit-box-shadow:2px 2px 3px #333333;
    box-shadow:2px 2px 3px #333333;
  }
  .main img{
    width:95vw ;
    height:40.4255vw;
  }
  .main p{
    color: white;
    position: absolute;
    bottom: 0px;
    padding-top: 12px;
    padding-bottom: 12px;
    left:50%;
    -webkit-transform:translateX(-50%);
    transform: translateX(-50%);
    width: 95vw;
    background-color: rgba(125, 125, 125, 0.5);
  }
  .list{
    width: 100%;
    height:22.95vw ;
    padding-top: 1vw;
    padding-bottom: 1vw;
    position: relative;
  }
  .list img{
    width:19.95vw ;
    height:19.95vw ;
    position: absolute;
    right: 2vw;
    margin-top: 2vw;
    margin-bottom: 2vw;
  }
  .list p{
    width:71.05vw ;
    line-break: auto;
    position: absolute;
    left: 1vw;
    top:50%;
    transform: translateY(-50%);
    }
  .list div{
    position: absolute;
    margin-left: 2.5vw;
    bottom: 0px;
    width: 90vw;
    height: 1px;
    border-bottom:1px solid #a9a9a9;
  }
  .list:last-child div{
    display: none;
  }




</style>
