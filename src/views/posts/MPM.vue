<template>
  <div>
    <post :proj="project">
      <template v-slot:content>
        <div class="text-container">
          <div class="text">
            <p>This is a material damage simulation project where a version of the Material Point Method was implemented in Unity. This is a simplified version of the traditional MPM method called The Moving least Squares(MLS)-MPM. This version simplifies some equations while making it much faster, allowing for real time simulations. The project was done in 3D using Unity with GPU instancing. The project paper can be found in the links section to the right.</p>
          </div>
        </div>
      </template>
    </post>
  </div>
</template>

<script>
import Post from '../../components/Post.vue';

export default {
  name: "MPM",
  components:{
    Post,
  },
  data(){
    return {
       project: 
        {
          id: 1,
          title: "MPM in Unity",
          images: [require("@/assets/portfolio/MPM/MPMDemo.gif")],
          media: [{video: false, source: require("@/assets/portfolio/MPM/MPMDemo.gif")}],
          date: "2020-12-15",
          page: "mpm",
          tools: "Unity",
          lang: "C#",
          github: "https://github.com/viktortholen/MPM_Unity",
          githubtext: "Material Point Method in Unity",
          paper: "SFX_Project_Report.pdf",
          credits: "Viktor Tholén"
        }
      
    }
  }
}
</script>

<style scoped>
</style>