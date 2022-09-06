<template>
  <div class="reward">
    <div class="reward_wrapper">
      <div class="reward_flex">
        <div class="reward_year_list">
          <div v-for="(i, n) in rewards"
            class="reward_year_item"
            :key="n"
            :class="{reward_underline: selected == n}"
            :style="{animationDelay: `${n*50}ms`}"
            @click="change(n)">
            <a>{{ i.year }}</a>
          </div>
        </div>

        <div class="reward_list">
          <p 
          v-for="(i, k) in reward_list"
          :key="k">{{ i }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Rewards from '@/static/resources/reward.json';

export default {
    name: 'rewards',
    data() {
        return { 
            rewards: Rewards.rewards,
            selected: 0,
            reward_list: []
        }
    },
    methods: {
        change: function(n) {
            this.selected = n;
            this.reward_list = this.rewards[n].reward;
        }
    },
    mounted() {
        this.reward_list = this.rewards[this.selected].reward;
    }
}
</script>

<style lang="scss">
@import "@/static/stylesheet/Rewards/style.scss";
</style>