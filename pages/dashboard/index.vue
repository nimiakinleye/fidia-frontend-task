<template>
  <div>
    <allNav />
    <div class="grid grid-cols-12">
      <div class="my_container">
        <h1>This is the home page, navigate to payments page for design</h1>
      </div>
    </div>
  </div>
</template>

<script>
import sidebar from '~/components/sidebar.vue'
import topbar from '~/components/topbar.vue'
import allNav from '~/components/allNav.vue'
export default {
  components: {
    sidebar,
    topbar,
    allNav,
  }
}
</script>

<style>
.my_container {
  @apply col-start-3
  col-end-13
  p-6
  mt-16
  opacity-90
}

</style>