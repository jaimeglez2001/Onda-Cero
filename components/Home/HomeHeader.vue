<template>
  <header class="header">
    <div class="user border-white border-2" v-if="ProfPic == ``">
      <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" fill="#ffffff" viewBox="0 0 256 256">
        <rect width="256" height="256" fill="none"></rect>
        <circle cx="128" cy="96" r="64" fill="none" stroke="#ffffff" stroke-miterlimit="10" stroke-width="16"></circle>
        <path d="M31,216a112,112,0,0,1,194,0" fill="none" stroke="#ffffff" stroke-linecap="round"
          stroke-linejoin="round" stroke-width="16"></path>
      </svg>
    </div>
    <div class="user" v-else>
      <img :src="ProfPic">
    </div>

    <div class="logo opacity-60"><img src="/logoxl.png" width="60px"></div>
  </header>
</template>

<script>
export default {
  props: ["ProfPic"]
}
</script>

<style lang="sass" scoped>
  .header
    @apply flex items-center justify-between p-5 fixed top-0 left-0 w-full z-10
    .user
      @apply w-10 h-10 object-cover rounded-full overflow-hidden flex justify-center items-center
      background-color: #42EC42
      img
        @apply z-20
      

</style>