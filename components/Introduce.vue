<template>
  <div class="introduce">
    <div class="introduce_wrapper">

      <h1 class="introduce_title">Teamlog가 창설된 2013년 이후...</h1>

      <div class="introduce_content_wrapper">
        <div 
        class="introduce_content"
        v-for="(i, k) in intro"
        :key="k"
        :style="{animationDelay: `${k*100}ms`}">
          <p>{{ i.category }}</p>
          <h1 class="introduce_content_title">{{ i.value }}</h1>
        </div>
      </div>

      <h1 class="introduce_title">특색</h1>
      
      <div class="introduce_content_wrapper"> 
        <div 
        class="introduce_content introduce_special"
        v-for="(i, n) in special"
        :key="n">
          <div class="introduce_special_wrapper">
            <img 
            class="introduce_special_image"
            :src="i.img">
            <div class="introduce_special_text">
              <h1>{{ i.title }}</h1>
              <p>{{ i.description }}</p>
            </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import config_json from '@/static/resources/config.json';
import intro_json from "@/static/resources/intro.json"; 


export default {
    name: "Introduce",
    data() {
      return {
        king: config_json.king,
        subking: config_json.subking,
        total: config_json.total_members,
        intro: intro_json.intro,
        special: undefined
      }
    },
    methods: {
    },
    mounted() {
      console.log(this.special)
      if (this.special == undefined) {
        this.special = intro_json.special;
        for (const element of this.special) {
          element.img = `/images/${element.img}`;
        }
      }
    }
}
</script>

<style lang="scss">
@import "@/static/stylesheet/Intro/style.scss";
</style>
