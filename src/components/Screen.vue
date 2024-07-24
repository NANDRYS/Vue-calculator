<script>
export default {
  props: {
    textOnScreen: {
      type: String,
      required: true
    }
  }
};
</script>

<template>
  <p>  {{ textOnScreen }}</p>
</template>

<style scoped>
p{
   width: 90%;
   height: 10vh;
   border-radius: 5px;
   display: block;
   position: absolute;
   text-align: right;
   padding: 10px;
   top: 3vh;
   left: 50%;
   transform: translateX(-50%);
   background-color: aqua;
}
</style>