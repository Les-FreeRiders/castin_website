<template>
  <div class="wave-container">
    <div style="display: flex" class="flex-column align-center justify-end h-100 w-100">
      <v-spacer />
      <h1 class="pa-10">{{ title }} <span style="font-family: Heimdal" v-if="$route.path !== '/about'">CAST'IN</span></h1>
      <v-spacer />
      <ScrollDownButton class="mb-12" href="#section-2" v-if="$route.path === '/roadmap'"/>
      <v-btn @click="$router.push('/roadmap')" id="roadmap" variant="outlined" rounded="xl"  v-if="$route.path !== '/roadmap'" style="margin-bottom: 50px">
        Roadmap
      </v-btn>
    </div>
  </div>
</template>
<script setup>

import ScrollDownButton from "@/components/header/ScrollDownButton.vue";
import '../../assets/css/font.css';
import { ref, defineProps } from "vue";
const props = defineProps({
  title: String,
});

</script>

<style scoped>


.wave-container {
    height: 40vh;
    background-color: rgb(var(--v-theme-primary));
    position: relative;
}


.wave-container::before {
    content: "";
    width: 100%;
    height: 77px;
    position: absolute;
    bottom: -0.3%;
    left: 0;
    background-size: auto;
    background-repeat: repeat no-repeat;
    background-position: 56vw bottom;
    background-image: url("data:image/svg+xml;utf8,<svg viewBox='0 0 1200  97' fill='none' xmlns='http://www.w3.org/2000/svg'><path d='M0 71L50 67C100 63 200 54 300 36C400 19 500 -8 600 1C700 10 800 54 900 71C1000 89 1100 80 1150 76L1200 71V98H1150C1100 98 1000 98 900 98C800 98 700 98 600 98C500 98 400 98 300 98C200 98 100 98 50 98H0V71Z' fill='%23ffffff'/></svg>");
}

@media (max-width: 850px) {
    .wave-container::before {
        height: 38.5px
    }
}

#logo {
    width: 50px;
    height: 50px;
    vertical-align: middle;
    margin-right: 5px
}


h1 {
    font-size: 2.5rem;
    text-align: center;
    font-family: 'Questrial', sans-serif;
    margin: 0;
    padding: 0;
    letter-spacing: 4px;
    color: rgb(var(--v-theme-on-primary));
    transition: all 0.5s ease-in-out;
}

h1 > span{
    color: rgb(var(--v-theme-secondary-darken-1));
}

@media (max-width: 700px) {
    #logo{
        width: 25px;
        height: 25px;
    }

    h1 {
        font-size: 1.5rem;
    }
}

h1 {
    transition: all 0.5s ease-in-out; /* Adjust animation duration and easing as needed */
}


</style>