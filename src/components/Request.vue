<template>
  <div class="hello bg-red-500 flex justify-center p-4">
    {{ name }}
  </div>
</template>

<script>
export default {
  name: 'Request',
  props: {
  },
  data() {
    return {
      name: "Request"
    }
  }
}
</script>
