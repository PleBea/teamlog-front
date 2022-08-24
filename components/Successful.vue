<template>
    <div class="successful">
        <div class="successful_wrapper">
            <div class="successful_title_wrapper">
                <h1 class="successful_title">축하드립니다!</h1>
            </div>

            <div class="successful_wrapper_people">
                <p 
                class="successful_people"
                v-for="(i, k) in successful"
                :key="k"
                :style="{animationDelay: `${k*100}ms`}"
                >{{ i }}</p>
            </div>

        </div>
    </div>
</template>

<script>
import successful_json from "@/static/resources/passlist.json";

export default {
    name: "Successful",
    data() {
        return {
            successful: successful_json.pass
        }
    },
    methods: {

    }
}
</script>

<style lang="scss">
@import "@/static/stylesheet/Successful/style.scss";
</style>