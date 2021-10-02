<template>
  <div class="main">
    <base-goal></base-goal>
    <base-goal></base-goal>
  </div>
</template>


<script>
import BaseGoal from '../UI/BaseGoal.vue'
export default {
  components:{BaseGoal}
}
</script>


<style>
.main{
  display: flex;
  flex-direction: row;
}
</style>
