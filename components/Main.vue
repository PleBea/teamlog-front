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


        <div class="main_wrapper_button">
          <button v-for="(i, g) in button_list"
          :key="g"
          class="main_button"
          >{{ i }}</button>          
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
    let button_list = ["소개", "커리큘럼", "합격자 목록"]
    let application = [Date.parse(config_json.club_application_start), Date.parse(config_json.club_application_end)]
    let now = new Date()
    let show = false
    config = {
      "background-image": `linear-gradient(rgba(20, 23, 32, 0.6), rgba(20, 23, 32, 0.6)), url("/images/${config}")`
    }

    if (now >= application[0] && now <= application[1]) {
      button_list.push('지원하기')
    }

    return{ 
      config,
      title,
      subtitle,
      show,
      button_list
    }
  },
  mounted() {
    this.show = true
  }
}
</script>

<style src="@/static/stylesheet/Main/style.scss" lang="scss"></style> 