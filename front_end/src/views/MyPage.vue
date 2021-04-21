<template>
<div>
  <div v-if="user">
    <div class="header">
      <div>
        <h1>{{user.name}}'s Page</h1>
        <p>A place to log pictures of your homework or tough problems to reference.</p>
      </div>
      <div>
        <p>
          <a @click="toggleUpload"><i class="pure-button">Upload</i></a>
          <a href="#" @click="logout"><i class="pure-button">Logout</i></a>
        </p>
      </div>
    </div>
    <escape-event @escape="escape"></escape-event>
    <uploader :show="show" @escape="escape" @uploadFinished="uploadFinished" />
    <image-gallery :photos="photos" />
  </div>
  <div v-else>
    <p>If you would like to upload photos or problem work, please register for an account or login.</p>
    <router-link to="/register" class="pure-button">Register</router-link> or
    <router-link to="/login" class="pure-button">Login</router-link>
  </div>
  <footer class="footer">
  <div class="container">
    <span class="text-muted"><a href="https://github.com/dmcbrid4/creative_project_5">Github: Hours spent: 7</a></span>
  </div>
</footer>
</div>
</template>

<script>
import EscapeEvent from '@/components/EscapeEvent.vue'
import Uploader from '@/components/Uploader.vue'
import ImageGallery from '@/components/ImageGallery.vue'
export default {
  name: 'mypage',
  components: {
    EscapeEvent,
    Uploader,
    ImageGallery
  },
  data() {
    return {
      show: false,
    }
  },
  computed: {
    user() {
      return this.$store.state.user;
    },
    photos() {
     return this.$store.state.photos;
   },
  },
  async created() {
    await this.$store.dispatch("getUser");
    await this.$store.dispatch("getMyPhotos");
  },
  methods: {
    async logout() {
      try {
        this.error = await this.$store.dispatch("logout");
      } catch (error) {
        console.log(error);
      }
    },
    escape() {
      this.show = false;
    },
    toggleUpload() {
      this.show = true;
    },
    async uploadFinished() {
      this.show = false;
      try {
        this.error = await this.$store.dispatch("getMyPhotos");
      } catch (error) {
        console.log(error);
      }
    },
  }
}
</script>


<style scoped>
.pure-button {
  margin: 0px 20px;
  background-color: #489F97;
  color: #fff;
}
.header {
  display: flex;
}
.header .button {
  margin-left: 50px;
  order: 2;
}
h1 {
  color: #A58153;
}
</style>