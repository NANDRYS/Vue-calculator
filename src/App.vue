<script>
import Numbers from './components/Numbers.vue'
import Screen from './components/Screen.vue'

export default {
  components: { Numbers, Screen },
  data() {
    return {
      textOnScreen: ''
    };
  },
  methods: {
    handleNumberClick(number) {
      this.textOnScreen += number;
    },
    checkResult(val){
      this.textOnScreen = Number(val);
    }
  }
};
</script>

<template>
  <div className="wrapper">
    <div className="body">
      <div className="screen">
        <Screen :textOnScreen="textOnScreen" />
      </div>
      <div className="butPanel">
        <Numbers @numberClicked="handleNumberClick" :text="'+'" />
        <Numbers @numberClicked="handleNumberClick" :text="'*'" />
        <Numbers @numberClicked="handleNumberClick" :text="'-'" />
        <Numbers @numberClicked="handleNumberClick" :text="'/'" />
        <Numbers @numberClicked="handleNumberClick" :text="1" />
        <Numbers @numberClicked="handleNumberClick" :text="2" />
        <Numbers @numberClicked="handleNumberClick" :text="3" />
        <Numbers @numberClicked="handleNumberClick" :text="4" />
        <Numbers @numberClicked="handleNumberClick" :text="5" />
        <Numbers @numberClicked="handleNumberClick" :text="6" />
        <Numbers @numberClicked="handleNumberClick" :text="7" />
        <Numbers @numberClicked="handleNumberClick" :text="8" />
        <Numbers @numberClicked="handleNumberClick" :text="9" />
        <Numbers @numberClicked="handleNumberClick" :text="0" />
        <Numbers @numberClicked="handleNumberClick" :text="'.'" />
        <Numbers @numberClicked="checkResult" :text="'='" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.screen{
  display: block;
  height: 18vh;
}
.body{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, 25%);
  width: 350px;
  height: 500px;
  background: #3c3c3c;
  border-radius: 30px;
}
.butPanel{
  display: grid ;
  grid-template-columns: repeat(4,1fr) ;
  gap: 20px;
  justify-items: center;

}
</style>
