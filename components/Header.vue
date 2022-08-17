<template>
    <div class="header">
        <nuxt-link
        class="header_left"
        :to="{path: '/'}" 
        >
            <img src="/images/teamlog_logo.png" alt="">
        </nuxt-link>
        <div class="header_right">
            <nuxt-link
            v-for="(i,k) in header_item"
            :key="k"
            :to="{path: i.url}"
            :class="{header_underline: i.url == $nuxt.$route.path}"
            >{{ i.name }}</nuxt-link>
        </div>
    </div>
</template>

<script>
import header_item from '@/static/resources/headerItem.json';

export default {
    setup() {

        return {
            header_item
        }
    }
}
</script>

<style src="@/static/stylesheet/Header/style.scss" lang="scss"></style>