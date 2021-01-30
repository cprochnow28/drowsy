<template>
  <div class="flex w-full h-full min-h-screen">
    <Requests class="w-1/5 box-border border-r border-gray-200"/>
    <Request class="w-2/5 box-border border-r border-gray-200"/>
    <Response class="w-2/5"/>
  </div>
</template>

<script>
import Request from './components/Request.vue'
import Requests from './components/Requests.vue'
import Response from './components/Response.vue'

export default {
  name: 'App',
  components: {
    Request,
    Requests,
    Response
  }
}
</script>
