<template>
  <div class="project">
    <div class="actions">
      <h3>{{ project.title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SingleProject',
  props: ['project']
}
</script>

<style>

</style>