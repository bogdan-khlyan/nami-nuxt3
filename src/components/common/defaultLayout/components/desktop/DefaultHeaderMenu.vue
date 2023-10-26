<template>
  <div class="default-header-menu">
    <div class="default-header-menu__item"
         :class="{'active': route.name === 'index' && isMenu}">
      <nuxt-link to="/?menu">
        <span>Меню</span>
      </nuxt-link>
    </div>
    <div class="default-header-menu__item"
         :class="{'active': route.name === 'delivery'}">
      <nuxt-link to="/delivery">
        <span>Доставка</span>
      </nuxt-link>
    </div>
    <div class="default-header-menu__item"
         :class="{'active': route.name === 'stocks'}">
      <nuxt-link to="/stocks">
        <span>Акции</span>
      </nuxt-link>
    </div>
    <div class="default-header-menu__item"
         :class="{'active': route.name === 'contacts'}">
      <nuxt-link to="/contacts">
        <span>Контакты</span>
      </nuxt-link>
    </div>
    <div class="default-header-menu__item"
         :class="{'active': route.name === 'reviews'}">
      <nuxt-link to="/reviews">
        <span>Отзывы</span>
      </nuxt-link>
    </div>
  </div>
</template>

<script setup>
import {useRoute} from "nuxt/app";

const route = useRoute()

const isMenu = false
</script>

<style lang="scss" scoped>
.default-header-menu {
  display: flex;
  margin-left: 180px;

  &__item {
    position: relative;
    margin-left: 7px;
    margin-right: 7px;
    cursor: pointer;
    transition: font-weight .4s ease-in-out;

    > a {
      padding: 10px 20px;

      font-family: Neucha, sans-serif;
      font-style: normal;
      font-weight: normal;
      font-size: 18px;
      line-height: 18px;
      text-decoration: none;

      letter-spacing: 0.08em;

      color: #FFFFFF;
    }

    &:after {
      transition: 0.3s;
      position: absolute;
      content: '';
      left: 20px;
      bottom: 0;
      width: 0;
      height: 2px;
      border-radius: 1px;

      background: #FAFAFA;
      z-index: -1;
    }

    &.active, &:hover {

      > a {
        font-weight: bold;
      }

      &:after {
        width: calc(100% - 42px);
        background: #FFFFFF;
      }

    }

    &:before {
      position: absolute;
      top: 7px;
      right: -10px;
      content: '';
      width: 5px;
      height: 5px;
      border-radius: 50%;
      background-color: #FFFFFF;
    }

    &:last-child {
      &:before { display: none }
    }

  }
}
</style>
