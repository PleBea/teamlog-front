<template>
  <div class="main">
    <div class="main_background" :style="config">
      <div class="main_wrapper">

        <div class="main_wrapper_title">
          <p v-for="(i, n) in title"
          :key="n"
          :class="[i=='LOG' ? 'main_title_sub' : 'main_title']"
          :style="{animationDelay: `${n*0.2}s`}"
          >{{ i }}</p>
        </div>
        
        <div class="main_wrapper_subtitle">
          <p  v-for="(i, k) in subtitle" 
          :key="k" 
          :class="[i=='Change' ? 'main_subtitle_sub' : 'main_subtitle']"
          :style="{animationDelay: `${k*0.2}s`}"
          >{{ i }}</p>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import config_json from "@/static/resources/config.json";

export default {
  name: "Main",
  setup() {
    let config = config_json.background_img
    let title  = ["TEAM", "LOG"]
    let subtitle = ["Feel", "the", "Change", "Make", "The", "Change"]
    let show = false
    config = {
      "background-image": `linear-gradient(rgba(20, 23, 32, 0.6), rgba(20, 23, 32, 0.6)), url("/static/images/${config}")`
    }

    return{ 
      config,
      title,
      subtitle,
      show
    }
  },
  mounted() {
    this.show = true
  }
}
</script>

<style src="@/static/stylesheet/Main/style.scss"></style> 