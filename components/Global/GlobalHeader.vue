<template>
  <header class="header">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="#ffffff" viewBox="0 0 256 256"><rect width="24" height="24" fill="none"></rect><line x1="216" y1="128" x2="40" y2="128" fill="none" stroke="#ffffff" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line><polyline points="112 56 40 128 112 200" fill="none" stroke="#ffffff" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></polyline></svg>
    <div class="header_info">
      <h1 class="header_title">{{PageTitle}}</h1>
      <div class="logo opacity-60"><img src="/logoxl.png" width="60px"></div>
    </div>
  </header>
</template>

<script>
export default {
  props: ["PageTitle"]
}
</script>

<style lang="sass" scoped>
  .header
    @apply flex flex-col p-5 w-full
    .header_info
      @apply flex justify-between items-center
      .header_title
        @apply font-semibold text-2xl
        color: #EDF7ED 

</style>