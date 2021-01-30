<template>
  <Request/>
  <Response/>
  <Requests/>
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
