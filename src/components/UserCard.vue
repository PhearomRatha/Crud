<script>
export default {
  props: {
    username: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
    isActive: {
      type: Boolean,
      default: false,
    },
    userInfo: {
      type: Object,
      default:() => {},
      required:true,

    },
  },
}
</script>

<template>
  <div>
    <p>{{ username }}</p>
    <p>{{ age }}</p>
    <p>{{ isActive ? 'Active' : 'inActive' }}</p>
    <p>{{ userInfo }}</p>
  </div>
</template>
