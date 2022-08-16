<template>
  <div class="curriculum">
    <div class="curriculum_wrapper">
      
    </div>
  </div>
</template>

<script>
import curriculum_json from '@/static/resources/curriculum.json';

export default {
  name: "Curriculum",
  setup() {
    let curriculum = curriculum_json.curriculum;

    return {
      curriculum
    }
  }
}
</script>

<style src="@/static/stylesheet/Curriculum/style.scss" lang="scss"></style>