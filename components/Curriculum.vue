<template>
  <div class="curriculum">
    <div class="curriculum_wrapper">

      <div 
      class="curriculum_item" 
      v-for="(i, k) in curriculum"
      :key="k">
        <h1>{{ i.name }}</h1>
        <p>{{ i.description }}</p>
      </div>

    </div>
  </div>
</template>

<script>
import curriculum_json from '@/static/resources/curriculum.json';

export default {
  name: "Curriculum",
    data() {
      return {
        curriculum: curriculum_json.curriculum
      }
    }
}
</script>

<style src="@/static/stylesheet/Curriculum/style.scss" lang="scss"></style>