<template>
    <div class="footer">
      <div class="text">
      <p>重庆邮电大学武装部军训助理宣传组</p>
      <p>Copyright © Littleor ALL Right Reserverd </p>
      </div>
    </div>
</template>

<script>
    export default {
        name: "footer"
    }
</script>

<style scoped>
.footer{
  position: relative;
  background-color: rgba(9,114,74,255);
  width: 100vw;
  height: 100px;
  text-align: center;
}
.text{
  padding-top:-50%;
  transform: translateY(50%);
}
  p{
    width: 100vw;
    color: white;
  }
</style>
