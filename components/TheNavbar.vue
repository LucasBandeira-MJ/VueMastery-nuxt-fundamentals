<template>
  <nav class="nav">
    <div class="logo">
      <nuxt-link to="/" class="logo text-lg">Nuxt Fundamentals
      <span class="subheader">A Vue School course</span>
    </nuxt-link>
    </div>
  </nav>
</template>

<script>
export default {
}
</script>

<style lang="stylus" scoped>
.nav
  display flex
  justify-content space-between
  align-items center
  margin-bottom 70px
  font-weight lighter
  letter-spacing .5px

  .logo
    display flex
    flex-direction column
    justify-content center

    .subheader
      opacity 0.70
      font-size .9rem
      color white
      padding-left 2px

  .nav-content
    font-size 1rem

    ul
      display flex
      list-style none

      li
        padding 2px 10px

        &:not(:first-of-type)
          border-left 1px solid rgb(255, 255, 255, 0.2);
</style>
