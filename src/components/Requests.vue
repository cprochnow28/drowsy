<template>
  <div class="flex-cols justify-center p-4 bg-gray-700">
    <!-- Header -->
    <div class="flex justify-center" id="header">
      <p class="flex align-center">Requests</p>
    </div>
    <!-- Creation Bar -->
    <div class="flex justify-center" id="creationBar">
      <input
        type="text"
        name="requestName"
        placeholder="request name"
        class="w-3/5 pl-2 px-1"
        v-model="requestName"
      />
      <button
        v-on:click="onSubmit"
        type="submit"
        class="rounded p-2 bg-green-400"
      >
        Add
      </button>
    </div>
    <!-- Request List -->
    <div class="flex justify-center" id="requestList">
      <ul>
        <li v-for="request in requests" v-bind:key="request">
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
