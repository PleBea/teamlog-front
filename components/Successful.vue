<template>
    <div class="successful">
        <div class="successful_wrapper">
            <h1 class="successful_title">축하드립니다!</h1>

            <div class="successful_wrapper_people">
                <p 
                class="successful_people"
                v-for="(i, k) in successful"
                :key="k"
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