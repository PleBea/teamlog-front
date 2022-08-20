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

        <hr class="main_hr">

        <div class="main_hover_mouse">
          <p>- 마우스를 올려주세요 -</p>
        </div>

        <div class="main_wrapper_button">
          <nuxt-link :to="{path: i.url }" v-for="(i, g) in header"
          :key="g"
          class="main_button"
          tag="button"
          >{{ i.name }}</nuxt-link>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
import config_json from "@/static/resources/config.json";
import header_item from "@/static/resources/headerItem.json";

export default {
  name: "Main",
  setup() {
    let config = config_json.background_img
    let title  = ["TEAM", "LOG"]
    let subtitle = ["Feel", "the", "Change", "Make", "The", "Change"]
    let application = [Date.parse(config_json.club_application_start), Date.parse(config_json.club_application_end)]
    let now = new Date()
    let show = false
    let header = header_item.header
    config = {
      "background-image": `linear-gradient(rgba(20, 23, 32, 0.6), rgba(20, 23, 32, 0.6)), url("/images/${config}")`
    }

    if (now >= application[0] && now <= application[1]) {
      header.push({
        url: "/application",
        name: "신청하기"
      })
    }

    return{ 
      config,
      title,
      subtitle,
      show,
      header
    }
  },
  mounted() {
    this.show = true
  }
}
</script>

<style src="@/static/stylesheet/Main/style.scss" lang="scss"></style> 