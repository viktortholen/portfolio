<template>
  <div  class="bar">
    <nav class="menu">
      <div id="marker"></div>
      <router-link class="btn" id="home" to="/" @click.native="indicator">Home</router-link>
      <!-- <router-link class="btn" id="About" to="/about" @click.native="indicator">CV</router-link> -->
      <router-link class="btn" id="Contact" to="/contact" @click.native="indicator">Contact</router-link>
      <a v-if="windowWidthComputed > 600" href="https://www.linkedin.com/in/viktor-tholen"><img class="linkedin-logo" src="../assets/linkedin_logo.png"/></a>
    </nav>
  </div>
</template>

<script>

export default {
  name: "Header",
  mounted(){
    window.addEventListener('resize', this.placeIndicator);
    this.placeIndicator();
  },
  data() {
    return{
        window: {
            width: 0,
            height: 0
        }
    }
  },
  created() {
      window.addEventListener('resize', this.handleResize);
      this.handleResize();
  },
  destroyed() {
      window.removeEventListener('resize', this.handleResize);
  },
  computed:{
    windowWidthComputed(){
      return this.window.width;
    }
  },
  methods: {
    handleResize() {
            this.window.width = window.innerWidth;
            this.window.height = window.innerHeight;
    },
    indicator: function (e){
      var marker= document.querySelector("#marker");
      marker.style.left = e.srcElement.offsetLeft + "px";
    },
    placeIndicator: function(){
      if(this.windowWidthComputed > 600){

        var marker = document.querySelector("#marker");
        var selected;

        if(this.$route.name === "About" || this.$route.name === "Contact" ){
          selected = document.querySelector("#" + this.$route.name);
        }
        else{
          selected = document.querySelector("#home");
        }
          marker.style.left = selected.offsetLeft + "px";
      }
    },
   

  }
};
</script>

<style scoped>

.dropdown{
  width: 100%;
}
.linkedin-logo{
  width: 1.7em;
  height: 1.7em;
  object-fit: cover;
  position: absolute;
  right: 2em;
  top: 1.5em;
}
#marker{
  position: absolute;
  height: 2px;
  width: 6.6em;
  background: white;
  text-decoration: none;
  margin-top: 3.5em;
  border-radius: 2rem;
  transition: 0.3s;
}
.home-link{
  height: 100%;
  width: 30%;
}
.bar {
  position: absolute;
  width: 100%;
  height: 5em;
  background: inherit;

}
.menu {
  height: 100%;
  width: 24em;
  display: flex;
  margin-left: 20%;
}
.btn {
  font-size: 1.1rem;
  border: none;
  background-color: inherit;
  cursor: pointer;
  display: inline-block;
  color: white;
  outline: none;
  margin: auto;
  width: 6em;
  text-decoration: none;
  text-align: center;
}
.btn:hover{
  font-weight: bold;
}
@media only screen and (max-width: 600px) {
  .menu {
    margin-left: 0;
  }
}
</style>