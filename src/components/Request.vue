<template>
  <div class="flex justify-left bg-white">
    <!-- Request Bar -->
    <div class="flex w-full h-12 border-b" id="request-bar">
      <form class="flex w-full" @submit.prevent="onSubmit">
        <select class="w-1/5 bg-white border-r pl-1" name="method" v-model="method">
          <option value="get" selected="selected">GET</option>
          <option value="post">POST</option>
          <option value="patch">PATCH</option>
          <option value="delete">DELETE</option>
        </select>

        <input type="text" name="url" placeholder="API URL" class="w-3/5 pl-2 px-1" v-model="url">

        <button type="submit" class="rounded p-2 w-1/5">Send</button>
      </form>
    </div>

    <!-- Message Bar -->

    <!-- Body -->
  </div>
</template>

<script>
export default {
  name: 'Request',
  props: {
  },
  data() {
    return {
      name: "Request",
      method: "",
      url: ""
    }
  },
  methods: {
    onSubmit() {
      console.log("Submitted!");
      console.log(this.method);
      console.log(this.url);
    }
  }
}
</script>
