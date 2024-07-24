<script>
import Numbers from './components/Numbers.vue'
import Screen from './components/Screen.vue'

export default {
  components: { Numbers, Screen },
  data() {
    return {
      textOnScreen: '',
      chars: ['+','-','*','/'],
      flag: true
    };
  },
  methods: {
    handleNumberClick(number) {
      this.textOnScreen += number;
    },
    checkResult(val){
      this.textOnScreen = eval(this.textOnScreen);
      this.flag= true
    },
    testing(){
      this.chars.forEach(element => {
        if(this.textOnScreen.includes(element)){
          return true
        }
      });
    }
    ,
    checkPoint(val){
      if(!this.textOnScreen.includes('.') || (this.textOnScreen.includes('.') && this.testing && this.flag)){
        if(!this.textOnScreen.includes('.')){
          this.textOnScreen += val;
        }else{
          this.textOnScreen += val;
          this.flag = false
        }
      }else{
        this.textOnScreen = this.textOnScreen
      }
    },
    clearScreen(){
      this.textOnScreen = ''
    },
    removeSumbol(){
      this.textOnScreen = this.textOnScreen.slice(0, -1)
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
        <Numbers @numberClicked="clearScreen" :text="'AC'" />
        <Numbers @numberClicked="removeSumbol" :text="'DEL'" />
        <Numbers @numberClicked="handleNumberClick" :text="'*'" />
        <Numbers @numberClicked="handleNumberClick" :text="'+'" />
        
        <Numbers @numberClicked="handleNumberClick" :text="'1'" />
        <Numbers @numberClicked="handleNumberClick" :text="'2'" />
        <Numbers @numberClicked="handleNumberClick" :text="'3'" />
        <Numbers @numberClicked="handleNumberClick" :text="'-'" />
        
        <Numbers @numberClicked="handleNumberClick" :text="'4'" />
        <Numbers @numberClicked="handleNumberClick" :text="'5'" />
        <Numbers @numberClicked="handleNumberClick" :text="'6'" />
        <Numbers @numberClicked="handleNumberClick" :text="'/'" />
        
        <Numbers @numberClicked="handleNumberClick" :text="'7'" />
        <Numbers @numberClicked="handleNumberClick" :text="'8'" />
        <Numbers @numberClicked="handleNumberClick" :text="'9'" />
        <Numbers @numberClicked="checkPoint" :text="'.'" />

        <Numbers @numberClicked="handleNumberClick" :text="'000'" />
        <Numbers @numberClicked="handleNumberClick" :text="'00'" />
        <Numbers @numberClicked="handleNumberClick" :text="'0'" />
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
  width: 90%;
  margin: 0 auto;
  grid-template-columns: repeat(4,1fr) ;
  gap: 20px;
  justify-items: center;

}
</style>
