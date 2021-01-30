<template>
  <div class="flex w-full h-full min-h-screen bg-charcoal-800">
    <Requests class="w-1/5 box-border border-r border-gray-500"/>
    <Request class="w-2/5 box-border border-r border-gray-500"/>
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
