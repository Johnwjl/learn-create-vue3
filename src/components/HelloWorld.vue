<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  },
  version: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <div class="green">
      {{ msg }}
      <span class="version">{{version}}</span>
    </div>
  </div>
</template>

<style scoped>
.green {
  font-size: 18px;
  font-weight: 200;
  margin: 20px 16px;
  .version {
    font-size: 12px;
    margin-left:10px;
  }
}
</style>
