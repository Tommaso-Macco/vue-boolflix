<template>
  <div>
      <h1>{{details.title}}</h1>
  </div>
</template>

<script>


export default {
  name: 'App',
  props: {
      details: Object,
  }
}
</script>

<style lang="scss">

</style>
