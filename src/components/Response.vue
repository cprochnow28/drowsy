<template>
  <div class="hello bg-red-500 flex justify-center p-4">
    {{ msg }}
  </div>
</template>

<script>
export default {
  name: 'Response',
  props: {
    msg: {
      type: String,
      required: false,
      default: "Hello"
    }
  }
}
</script>
