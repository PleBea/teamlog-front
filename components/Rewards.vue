<template>
  <div class="reward">
    <div class="reward_wrapper">
      <a v-for="(i, n) in rewards"
      :key="n"
      :class="{reward_underline: selected == n}"
      @click="change(n)">
      {{ i.year }}</a>

      <p v-for="(i, k) in reward_list"
      :key="k">{{ i }}</p>
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
        change(n) {
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