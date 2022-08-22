<template>
  <Reward></Reward>
</template>

<script>
import Reward from '../components/Rewards.vue'
import Reward_json from '@/static/resources/reward.json';

export default {
    name: 'RewardPage',
    setup() {
        let Reward = Reward_json.rewards;
        return {
            Reward
        }
    },
    components: {
      Reward
    }
}
</script>

<style>

</style>