<template>
  <div>
    <p v-bind:style="{ color: 'aqua', fontSize: '123px' }">adsfsgdfs</p>

    <p v-bind:style="{ color: colorColor, fontSize: '143px' }">adsfsgdfsdfs</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      colorColor: 'red',
    }
  },
}
</script>

<style></style>
