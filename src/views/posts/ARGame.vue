<template>
  <div>
    <post :proj="project">
      <template v-slot:content>
        <div class="text-container">
          <div class="text">
            <p>This is my Bachelor Project that I did together with five other students. The game is called Alien Invasion and is a turn based multiplayer game for two players. It can be played on mobile devices with cameras. I primarily did the game logic but worked on the networking and AR functionality as well. The game is made in Unity and uses a server-client model.</p>
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
          title: "AR Game",
          media: [{video: false, source: require("@/assets/portfolio/ARGame/game_board.jpg")}, {video: false, source: require("@/assets/portfolio/ARGame/game_hit.jpg")}, {video: false, source: require("@/assets/portfolio/ARGame/game_select.jpg")}, {video: false, source: require("@/assets/portfolio/ARGame/Map.png")}],
          date: "2020-05-17",
          page: "argame",
          tools: "Unity",
          lang: "C#",
          github: "https://github.com/viktortholen/AR-Game",
          githubtext: "AR Game",
          credits: "Viktor Tholén, Rebecka Ljung, Jonas Bertilson, Simon Brefält, Oscar Johansson, Daniel Hägglund"
        }
      
    }
  }
}
</script>

<style scoped>
</style>