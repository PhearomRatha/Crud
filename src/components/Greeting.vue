<script>
export default {
  data() {
    return {}
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    greeting: {
      type: String,
      default: 'Hello',
      required: true,
    },
  },
}
</script>
<template>
  <div>
    <!-- <p>{{ propValue }}</p> -->
    <!-- <p>{{ UserName }}</p> -->
    <p>{{ name }}</p>
    <p>{{ greeting }},{{ name }}</p>
  </div>
</template>
