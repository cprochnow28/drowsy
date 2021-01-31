<template>
  <div class="flex-cols justify-center bg-gray-700 text-white">
    <!-- Header -->
    <div class="h-12 flex justify-center items-center" id="header">
      <p class="flex items-center">Requests</p>
    </div>
    <!-- Creation Bar -->
    <div class="h-12 flex justify-center" id="creationBar">
      <input
        type="text"
        name="requestName"
        placeholder="request name"
        class="w-3/5 pl-2 px-1 text-black"
        v-model="requestName"
      />
      <button
        @click="onSubmit"
        type="submit"
        class="p-2 bg-green-400"
      >
        Add
      </button>
    </div>
    <!-- Request List -->
    <div class="flex mt-2 w-full" id="requestList">
      <ul class="w-full">
        <li v-for="request in requests" :key="request" @click="setActiveFile" :class="`w-full pl-4 h-8 flex items-center ${activeFile === request.title ? 'bg-charcoal-600' : ''}`">
          {{ request.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Requests",
  props: {
  },
  data() {
    return {
      requestName: "",
      requests: [],
      activeFile: ""
    };
  },
  methods: {
    onSubmit() {
      if (!this.requests.some(request => request.title === this.requestName)) {
        this.requests.push({ title: this.requestName });
        this.activeFile = this.requestName;
      }
      this.requestName = "";
    },
    setActiveFile(event) {
      this.activeFile = event.target.innerHTML;
    }
  },
};
</script>
