<template>
  <header class="hello grid-wrapper">
    <navigation></navigation>
    <div class="hello-text">
      <h1 class="hello-title"><img src="../assets/logo11.png"></h1>
    </div>
    <div class="hello-timer">
      <h2 class="timer-head">Next race start at:</h2>
      <countdown date="June 24, 2018 16:10"></countdown>
    </div>
    <img class="hello-img" src="../assets/carB.png">
    <p class="hello-paragraph">Jeśli jest fanem sportów wyścigowych i zastanawiałeś się jak poradziłbyś sobie w roli inżyniera wyścigowego ta gra jest zdecydowanie dla ciebie!Ustaw swój samochód,przejdź okrążenie w jak najkrótszym czasie i wygrywaj realne nagrody.Walcz o prymat z setkami innych inżynierów ,dołącz do Eleven Race!</p>
  </header>
</template>

<script>
import countdown from './countdown.vue'
import navigation from './navigation.vue';

export default {
  name: 'home',
  data () {
    return {
      showMenu: false,
      isActive: false,
    }
  },
  methods: {
    changeMenu: function() {
      if(this.isActive==true){
        this.isActive=false
      }
      else{
        this.isActive=true
      }
    }
  },
  components:{
    countdown,
    navigation
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello-paragraph{
  margin-top:60%;
  padding:2%;
  text-align: center;
  font-size: 18px;
}
.timer-head{
  text-transform: uppercase;
  font-weight: 200;
  margin: 2% 0;
  color: #eeebe8;
  font-size: 36px;
}
.timer-time{
  font-size: 24px;
}
.hello-timer{
  text-align: center;
  grid-column: 2 / 5;
  grid-row: 2;
}
.hello-img{
  position:absolute;
  width: 100%;
  z-index: 1;
  top:35%;
}
.list-item.active{
  display:block;
}
.list-icon{
  font-size:28px;
  color:#aed434;
}
button{
  text-align: center;
  display: inline;
}
h1 span{
  color:#aed434;
}
.hello{
  padding-top: 2%;
  background: radial-gradient(ellipse at center, #37393d 0%,#16171a 100%);
  height: 100vh;
}
.hello-text{
  text-align: center;
  margin:4%;
  margin-bottom: 2%;
}
.hello-title{
  display: inline;
  margin:0;
}
.hello-nav{
  position: relative;
  margin:4%;
  overflow: hidden;
  z-index: 2;
}
.hello-nav-list{
  margin: 0;
  padding: 0;
  text-align: center;
  font-size: 18px;
}
.list-item{
  list-style: none;
  display: none;
  padding:2%;
  text-transform: uppercase;
}
.list-item a{
  color:#aed434;
  text-decoration: none;
  display: inline-block;
}
.list-item a::after{
  content: '';
  display: block;
  width: 0;
  height: 2px;
  background: #aed434;
  transition: width .4s;
}
.list-item a:hover::after{
  width: 100%;
  transition: width .4s;
}

@media (min-width: 600px){
  .list-item{
    display: inline-block;
  }
  .list-icon{
    display: none;
  }
  .grid-wrapper{
    display: grid;
    grid-template-columns: 1fr 2fr 2fr 3fr 1fr;
    grid-template-rows: 1fr 1fr 3fr 1fr;
    grid-gap: 20px;
  }
  .hello-nav{
    margin-top:0;
    grid-column: 4 / 5;
    grid-row: 1;
  }
  .hello-text{
    grid-column: 2 / 3;
    grid-row: 1;
  }
  .hello-img{
    width: auto;
    top:10%;
    left:7%;
  }
  .hello-paragraph{
    grid-column: 2 / 5;
    grid-row: 4;
    margin-top:0;
    padding:0;
    text-align: left;
  }
}

</style>
