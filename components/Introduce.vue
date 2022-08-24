<template>
  <div class="introduce">
    <div class="introduce_wrapper">
      <div class="introduce_content_wrapper">
        <h1 class="introduce_title">Introduce</h1>

        <div class="introduce_content">
          <div class="introduce_content">
            
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import config_json from "@/static/resources/config.json";

export default {
    name: "Introduce",
    setup() {
        let king = config_json.king;
        let subking = config_json.subking;

        return {
            king,
            subking
        }
    }
}
</script>

<style lang="scss">
@import "@/static/stylesheet/Intro/style.scss";
</style>
