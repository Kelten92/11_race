<template>
    
        <nav role="navigation" class="hello-nav">
            <ul class="hello-nav-list">
                <i class="list-icon fas fa-bars" v-on:click="changeMenu"></i>
                <li class="list-item" v-bind:class="{ active: isActive }"><a href="#">Home</a></li>
                <li class="list-item" v-bind:class="{ active: isActive }"><a href="#">About</a></li>
                <li class="list-item" v-bind:class="{ active: isActive }"><a href="#">Login</a></li>
                <li class="list-item" v-bind:class="{ active: isActive }"><a href="#">Register</a></li>
                <li class="list-item" v-bind:class="{ active: isActive }"><a href="#">Contact</a></li>
            </ul>
        </nav>
       
    
</template>
<style scoped>

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
.list-item.active{
  display:block;
}
.list-icon{
  font-size:28px;
  color:#aed434;
}


@media (min-width: 600px){
  .list-item{
    display: inline-block;
  }
  .list-icon{
    display: none;
  }
  .hello-nav{
    margin-top:0;
    grid-column: 4 / 5;
    grid-row: 1;
  }
  

}
</style>
<script>
export default {
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
}
</script>

