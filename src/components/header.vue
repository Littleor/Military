<template>
  <div class="header">
    <div id="scroll" class="scroll">
      <img src="../assets/header.jpg">
      <p><b>重邮小卫士</b></p>
      <p>军训特辑</p>
    </div>

    <div id="fix" class="fix">
      <img src="../assets/header.jpg">
      <p><b>重邮小卫士-军训特辑</b></p>
    </div>
  </div>
</template>

<script>
    export default {
        name: "header"
    }
</script>

<style scoped>
  .header{
    width: 100vw;
    text-align: center;
    background-color: rgba(9,114,74,255);
    -moz-box-shadow:0px 2px 5px #333333;
    -webkit-box-shadow:0px 2px 5px #333333;
    box-shadow:0px 2px 5px #333333;
  }
  .scroll{
    //display: none;
  }
  .scroll img{
    margin-top: 30px;
    width: 35vw;
    height: 35vw;
    border-radius: 35vw;
    border: white 4px solid;
    -webkit-animation:myRoxtate 1s ease infinite;
    animation:myRotate 1s ease infinite;
    animation-iteration-count:1;
    -webkit-animation-iteration-count:1;
  }


  .scroll img:hover{
    -webkit-animation:myRoxtate 1s ease infinite;
    animation:myRotate 1s ease infinite;
  }
  @-webkit-keyframes myRotate{
    0%{ -webkit-transform: rotate(0deg);}
    100%{ -webkit-transform: rotate(360deg);}
  }
  @keyframes myRotate{
    0%{ -webkit-transform: rotate(0deg);}
    100%{ -webkit-transform: rotate(360deg);}
  }
  p{
    margin: 0;
    color:white;

  }
  .scroll img + p{
    margin-top: 3px;
    font-size: large;

  }
  .scroll p+p{
    font-size: small;
    padding-bottom: 20px;
  }
  .fix{
    background-color: rgba(9,114,74,255);
    opacity: 0;
    position: fixed;
    top:0;
    width: 100vw;
    height: 68px;
    z-index: 10;

  }

  .fix img{
    position: absolute;
    left:7px;
    top:7px;
    width: 50px;
    height: 50px;
    border-radius: 50px;
    border: white 2px solid;
  }
  .fix img:hover{
    -webkit-animation:Roxtate 1s ease infinite;
    animation:Rotate 1s ease infinite;
  }
  @-webkit-keyframes Rotate{
    0%{ -webkit-transform: rotate(0deg);}
    100%{ -webkit-transform: rotate(360deg);}
  }
  @keyframes Rotate{
    0%{ -webkit-transform: rotate(0deg);}
    100%{ -webkit-transform: rotate(360deg);}
  }
  .fix p{
    position: relative;
    margin: auto;
    line-height: 68px;
    font-size:20px;
  }


</style>
