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
        <li v-for="request in requests" :key="request" class="first:bg-charcoal-600 w-full pl-4 h-8 flex items-center">
          {{ request.title }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Requests",
  props: {},
  data() {
    return {
      requestName: "",
      requests: [],
    };
  },
  methods: {
    onSubmit() {
      this.requests.push({ title: this.requestName });
    },
  },
};
</script>
