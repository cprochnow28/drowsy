<template>
  <div class="hello bg-red-500 flex justify-center p-4">
    {{ name }}
  </div>
</template>

<script>
export default {
  name: 'Response',
  props: {
  },
  data() {
    return {
      name: "Response"
    }
  }
}
</script>
