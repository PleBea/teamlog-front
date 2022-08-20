<template>
  <div class="introduce">
    <div class="introduce_wrapper">
      <h1 class="introduce_title">Introduce</h1> 
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
