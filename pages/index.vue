<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-scroll-y-reverse-transition>
        <v-card class="logo py-4 d-flex justify-center my-auto" height="600" v-if="showPrincipalCard" shaped>
          <v-card-text>
            <v-row>
              <v-col md="4">
                <v-img height="520" width="170" src="https://pbs.twimg.com/media/EdArQZEXoAA8KbS?format=jpg&name=900x900"
                       alt="jonathan_image"></v-img>
              </v-col>
              <v-col md="8" class="mt-md-10">
                <v-scroll-x-transition>
                  <v-alert
                    v-if="showFirstItem"
                    color="teal lighten-1"
                    outlined
                    shaped
                  >
                    <span><strong>Nome</strong>: Jonathan Malagueta da Costa</span>
                  </v-alert>
                </v-scroll-x-transition>
                <v-scroll-x-transition>
                  <v-alert
                    color="teal lighten-1"
                    v-if="showSecondItem"
                    outlined
                    shaped
                  >
                    <span><strong>Idade</strong>: 23 anos</span>
                  </v-alert>
                </v-scroll-x-transition>
                <v-scroll-x-transition>
                  <v-alert
                    v-if="showThirdItem"
                    color="teal lighten-1"
                    outlined
                    shaped
                  >
                    <span><strong>Fullstack developer</strong></span>
                  </v-alert>
                </v-scroll-x-transition>
                <v-row class="mt-md-15 ml-md-1">
                  <v-scroll-x-transition>
                    <v-alert
                      color="teal lighten-1"
                      outlined
                      v-if="showLastItem"
                      shaped
                      width="300"
                    >
                      <p>Redes sociais</p>
                      <v-row>
                        <v-col md="2">
                          <a href="https://www.linkedin.com/in/jonathan-malagueta-524391150/?msgControlName=reply_to_sender&msgConversationId=2-NDZhMjM0ZDctODJjOC00ODc0LTlmYzgtZWExN2ZkOGMzYmY3XzAxMg%3D%3D&msgOverlay=true"><v-icon color="teal lighten-1">mdi-linkedin</v-icon></a>
                        </v-col>
                        <v-col md="2">
                          <a href="https://github.com/LofiJon"><v-icon color="teal lighten-1">mdi-github</v-icon></a>
                        </v-col>
                        <v-col md="2">
                          <a href="https://www.instagram.com/lofijon/"><v-icon color="teal lighten-1">mdi-instagram</v-icon></a>
                        </v-col>
                      </v-row>
                    </v-alert>
                  </v-scroll-x-transition>
                </v-row>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-scroll-y-reverse-transition>

    </v-col>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'IndexPage',
  data(){
    return {
      showPrincipalCard: true as boolean,
      showFirstItem: false as boolean,
      showSecondItem: false as boolean,
      showThirdItem: false as boolean,
      showLastItem: false as boolean
    }
  },
  async mounted() {
    await setTimeout(() => {
      this.showPrincipalCard = true
    }, 2000)
    await setTimeout(() => {
      this.showFirstItem = true
    }, 3000)
    setTimeout(() => {
      this.showSecondItem = true
    }, 4000)
    setTimeout(() => {
      this.showThirdItem = true
    }, 5000)
    setTimeout(() => {
      this.showLastItem = true
    }, 7000)
  }
});
</script>

<style scoped>
body {
  font-family: tahoma;
  height: 100vh;
  background-image: url(https://picsum.photos/g/3000/2000);
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
}

a {
  text-decoration: none;
}

.our-team {
  padding: 30px 0 40px;
  margin-bottom: 30px;
  background-color: #f7f5ec;
  text-align: center;
  overflow: hidden;
  position: relative;
}

.our-team .picture {
  display: inline-block;
  height: 130px;
  width: 130px;
  margin-bottom: 50px;
  z-index: 1;
  position: relative;
}

.our-team .picture::before {
  content: "";
  width: 100%;
  height: 0;
  border-radius: 50%;
  background-color: #1369ce;
  position: absolute;
  bottom: 135%;
  right: 0;
  left: 0;
  opacity: 0.9;
  transform: scale(3);
  transition: all 0.3s linear 0s;
}

.our-team:hover .picture::before {
  height: 100%;
}

.our-team .picture::after {
  content: "";
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #1369ce;
  position: absolute;
  top: 0;
  left: 0;
  z-index: -1;
}

.our-team .picture img {
  width: 100%;
  height: auto;
  border-radius: 50%;
  transform: scale(1);
  transition: all 0.9s ease 0s;
}

.our-team:hover .picture img {
  box-shadow: 0 0 0 14px #f7f5ec;
  transform: scale(0.7);
}

.our-team .title {
  display: block;
  font-size: 15px;
  color: #4e5052;
  text-transform: capitalize;
}

.our-team .social {
  width: 100%;
  padding: 0;
  margin: 0;
  background-color: #1369ce;
  position: absolute;
  bottom: -100px;
  left: 0;
  transition: all 0.5s ease 0s;
}

.our-team:hover .social {
  bottom: 0;
}

.our-team .social li {
  display: inline-block;
}

.our-team .social li a {
  display: block;
  padding: 10px;
  font-size: 17px;
  color: white;
  transition: all 0.3s ease 0s;
  text-decoration: none;
}

.our-team .social li a:hover {
  color: #1369ce;
  background-color: #f7f5ec;
}

</style>
