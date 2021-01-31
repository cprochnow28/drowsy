<template>
  <div class="flex">
    <form class="flex w-full flex-col" @submit.prevent="onSubmit">
    <!-- Request Bar -->
    <div class="flex w-full h-12 border-b border-gray-500 bg-white" id="request-bar">

        <select class="w-1/5 border-r bg-white pl-1" name="method" v-model="method">
          <option value="GET">GET</option>
          <option value="POST">POST</option>
          <option value="PATCH">PATCH</option>
          <option value="DELETE">DELETE</option>
        </select>

        <input type="text" id="url" name="url" @focus="resetURL" placeholder="API URL" class="w-3/5 pl-2 px-1" v-model="url">

        <button type="submit" class="rounded p-2 w-1/5">Send</button>

    </div>

    <!-- Message Bar -->

    <div class="flex w-full h-12 border-b border-gray-500 bg-white" id="message-bar">
      <select class="w-1/5 border-r pl-1 bg-white" id="body-type" @focus="resetBodyType" v-model="bodyType">
        <option value="" disabled hidden>Body</option>
        <option value="XML">XML</option>
        <option value="JSON">JSON</option>
      </select>
    </div>

    <!-- Body -->

    <textarea class="flex w-full h-full p-4 text-white bg-transparent" v-model="body" id="body">

    </textarea>

    </form>
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
      method: "GET",
      url: "",
      bodyType: "",
      body: ""
    }
  },
  methods: {
    onSubmit() {
      if (!this.url) {
        document.getElementById("url").classList.add("border-red-500");
        document.getElementById("url").classList.add("border-4");
        alert(`Please Provide an API URL to ${this.method}`);
      } else if (!this.bodyType) {
        document.getElementById("body-type").classList.add("border-red-500");
        document.getElementById("body-type").classList.add("border-4");
        alert(`Please Provide a body type.`);
      } else {
        console.log("Submitted!");
        alert(`Submitted!\n\nMethod: ${this.method}\nURL: ${this.url}\nBody Type: ${this.bodyType}`)
        console.log(this.body);
      }
    },
    resetURL() {
      document.getElementById("url").classList.remove("border-4");
      document.getElementById("url").classList.remove("border-red-500");
    },
    resetBodyType() {
      document.getElementById("body-type").classList.remove("border-4");
      document.getElementById("body-type").classList.remove("border-red-500");
    }
  }
}
</script>
