<template>
  <header class="default-header-desktop">
    <div class="default-header-desktop__content">
      <nuxt-link class="default-header-desktop__content--logo"
                 to="/?menu"
                 ref="logo">
        <logo-vertical-icon/>
      </nuxt-link>
      <default-header-menu/>
    </div>
  </header>
</template>

<script setup>
import LogoVerticalIcon from "@/components/common/icons/LogoVerticalIcon.vue";
import DefaultHeaderMenu from "@/components/common/defaultLayout/components/desktop/DefaultHeaderMenu.vue";
</script>

<style scoped lang="scss">
.default-header-desktop {
  position: fixed;
  z-index: 999;

  box-sizing: border-box;

  width: 100%;
  max-width: 100%;
  height: 88px; // 120

  transition: all 300ms ease-in-out;

  background-color: #0e4262;

  &__content {
    max-width: 1200px;
    margin: 0 auto;

    position: relative;
    display: flex;
    align-items: center;
    height: 88px;
    transition: 300ms;

    &--logo {
      position: absolute;
      top: -20px;
      left: -40px;

      display: flex;
      justify-content: center;
      align-items: center;

      width: 204px;
      height: 204px;
      border-radius: 50%;

      background: #FFFFFF;
      box-shadow: 0px 0px 52px rgba(0, 0, 0, 0.16);
      cursor: pointer;

      transition: 0.5s;

      :deep(svg) {
        transition: 0.5s;
      }
    }
  }

}
</style>
