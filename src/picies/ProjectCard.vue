<script>
import { RouterLink } from 'vue-router';

export default {
  name: 'ProjectCard',
  props: {
    card: String
  },
}
</script>

<template>
 <div class="card" style="width: 18rem;">
  <img v-if="card.img_url.startsWith('http')" :src="card.img_url" class="card-img-top">
  <img v-else :src="'http://127.0.0.1:8000/storage/' + card.img_url" class="card-img-top">
  <div class="card-body">
    <h5 class="card-title">{{card.title}}</h5>
    <!-- <p class="card-text">{{ card.description }}</p> -->
    <RouterLink :to="{ name: 'project', params: {id: card.id}  }" class="btn btn-primary">More</RouterLink>
  </div>
</div>
</template>

<style scoped>

</style>
