<template>
  <div>
    <p v-if="age >= 18">成年了</p>
    <p v-else-if="age < 18 && age >= 12">少年</p>
    <p v-else>儿童</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      age: 10,
    };
  },
  methods: {},
};
</script>

<style></style>
