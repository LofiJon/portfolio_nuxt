<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-scroll-y-reverse-transition>
        <v-card class="card__info py-7 justify-center my-auto" height="600" v-if="showPrincipalCard" shaped>
          <v-card-text>
            <v-row>
              <v-col md="4" sm="6" xs="2">
                <v-img height="520" width="170" src="https://pbs.twimg.com/media/EdArQZEXoAA8KbS?format=jpg&name=900x900"
                       alt="jonathan_image"></v-img>
              </v-col>
              <v-col md="8" sm="6" xs="2" class="mt-md-10">
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
                <v-row class="mt-15 ml-md-1">
                  <v-scroll-x-transition>
                    <v-alert
                      color="teal lighten-1"
                      outlined
                      v-if="showLastItem"
                      shaped
                    >
                      <p>Redes sociais</p>
                      <v-row>
                        <v-col md="2" xs="2">
                          <a href="https://www.linkedin.com/in/jonathan-malagueta-524391150/?msgControlName=reply_to_sender&msgConversationId=2-NDZhMjM0ZDctODJjOC00ODc0LTlmYzgtZWExN2ZkOGMzYmY3XzAxMg%3D%3D&msgOverlay=true"><v-icon color="teal lighten-1">mdi-linkedin</v-icon></a>
                        </v-col>
                        <v-col md="2" xs="2">
                          <a href="https://github.com/LofiJon"><v-icon color="teal lighten-1">mdi-github</v-icon></a>
                        </v-col>
                        <v-col md="2" xs="2">
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
  background-size: cover;
  background-position: center;
  display: flex;
  align-items: center;
}

a {
  text-decoration: none;
}
.card__info {
  border-left: #00796B solid 4px;
}

</style>
