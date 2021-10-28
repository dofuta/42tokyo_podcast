<template>
  <div>
    <Header />
    <b-container>
      <Service />
      <Service />
      <Service />
      <Service />
      <Service />
      <Service />
    </b-container>
  </div>
</template>

<script>
import Service from '~/components/Service.vue'

export default {
  components: {
    Service
  },
  methods: {
  }
}
</script>
