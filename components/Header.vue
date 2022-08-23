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
            v-for="(i,k) in header"
            :key="k"
            :to="{path: i.url}"
            :class="{header_underline: i.url == $nuxt.$route.path}"
            >{{ i.name }}</nuxt-link>
        </div>
    </div>
</template>

<script>
import config_json from '@/static/resources/config.json';

export default {
    name: 'Header',
    data() {
        return {
            header: {}
        }
    },
    methods: {

    },
    mounted() {
        let header_item = require('@/static/resources/headerItem.json');
        let tmp = header_item.header;
        let now = new Date()
        let application = [Date.parse(config_json.club_application_start), Date.parse(config_json.club_application_end)]
        let application_object = {
            url: "/application",
            name: "신청하기"
        }

        if (now >= application[0] && now <= application[1] && tmp.length < 5) {
            tmp.push(application_object)
        }

        this.header = tmp
    }
}
</script>

<style src="@/static/stylesheet/Header/style.scss" lang="scss"></style>