<template>
  <div class="flex w-full h-full">
    <Requests class="w-1/5 border-r"/>
    <Request class="w-2/5 border-r"/>
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
