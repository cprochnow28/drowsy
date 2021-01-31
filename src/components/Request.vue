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
        <option value="" disabled hidden>Type</option>
        <option value="JSON">JSON</option>
        <option value="XML">XML</option>
      </select>
      <select class="w-1/5 border-r pl-1 bg-white hidden" id="header-type" @focus="resetHeaderType" v-model="headerType">
        <option value="JSON">JSON</option>
        <option value="XML">XML</option>
      </select>
      <button type="button" class="px-2" id="headers-toggle-button" @click="toggleHeaders" v-text="headersToggleText"></button>
    </div>

    <!-- Message -->
    <div id="message" class="w-full h-full">
      <!-- Body -->
      <textarea class="flex w-full h-full p-4 text-white bg-transparent resize-none" v-model="body" id="body">

      </textarea>
      <!-- Header -->
      <textarea class="hidden flex w-full h-full p-4 text-white bg-transparent resize-none" v-model="headers" id="headers">

      </textarea>
    </div>

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
      body: "",
      headers: "",
      headerType: "",
      headersToggleText: "Body"
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
        let data = {
          "lol": "memes",
          "dreams": {
          "themes": "hemes"
          },
          "LolDude": "YallDude"
        };
        console.log(data);
        alert(`Submitted!\n\nMethod: ${this.method}\nURL: ${this.url}\nBody Type: ${this.bodyType}`)
        console.log(this.body);
        console.log(this.headers);
      }
    },
    toggleHeaders() {
      let headersElement = document.getElementById("headers");
      let bodyElement = document.getElementById("body");
      let headerTypeElement = document.getElementById("header-type");
      let bodyTypeElement = document.getElementById("body-type");
      if (headersElement.classList.contains("hidden")) {
        headersElement.classList.remove("hidden");
        bodyElement.classList.add("hidden");
        headerTypeElement.classList.remove("hidden");
        bodyTypeElement.classList.add("hidden");
        this.headersToggleText = "Headers";
      } else {
        headersElement.classList.add("hidden");
        bodyElement.classList.remove("hidden");
        headerTypeElement.classList.add("hidden");
        bodyTypeElement.classList.remove("hidden");
        this.headersToggleText = "Body";
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
