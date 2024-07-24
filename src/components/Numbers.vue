<script>
export default {
  props: {
    text: {
      type: String,
      required: true
    }
  }
};
</script>

<template>
  <button className="but" @click="$emit('numberClicked', text)">
    {{ text }}
  </button>
</template>

<style scoped>
.but{
   text-align: center;
   line-height: 7vh;
   display: block;
   width: 7vh;
   height: 7vh;
   background: #36d5fa;
   border-radius: 10px;
   box-shadow: 0 0 10px black;
}
.but:hover, .but:active{
   background: #3645fa;
}
</style>