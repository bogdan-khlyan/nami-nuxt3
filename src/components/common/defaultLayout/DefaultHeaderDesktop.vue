<template>
  <header class="default-header-desktop"
          :class="{'show': show}"
          ref="header">
    <div class="default-header-desktop__content">
      <nav class="default-header-desktop__nav">
        <nuxt-link class="default-header-desktop__nav--logo"
                   to="/?menu"
                   ref="logo">
          <logo-vertical-icon/>
        </nuxt-link>
        <div class="default-header-desktop__nav--menu">
          <div class="item"
               :class="{'active': $route.name === 'index' && isMenu}">
            <nuxt-link to="/?menu">
              <span>Меню</span>
            </nuxt-link>
          </div>
          <div class="header__nav--menu--item"
               :class="{'active': $route.name === 'delivery'}">
            <nuxt-link to="/delivery">
              <span>Доставка</span>
            </nuxt-link>
          </div>
          <div class="header__nav--menu--item"
               :class="{'active': $route.name === 'stocks'}">
            <nuxt-link to="/stocks">
              <span>Акции</span>
            </nuxt-link>
          </div>
          <div class="header__nav--menu--item"
               :class="{'active': $route.name === 'contacts'}">
            <nuxt-link to="/contacts">
              <span>Контакты</span>
            </nuxt-link>
          </div>
          <div class="header__nav--menu--item"
               :class="{'active': $route.name === 'reviews'}">
            <nuxt-link to="/reviews">
              <span>Отзывы</span>
            </nuxt-link>
          </div>
        </div>
      </nav>
    </div>
  </header>
</template>

<script setup>
import LogoVerticalIcon from "@/components/common/icons/LogoVerticalIcon.vue";

const isMenu = true
const show = true
</script>

<style scoped lang="scss">
.show {
  height: 88px!important;

  background-color: #0e4262;

  .header__nav {
    height: 88px!important;

    .header__nav--logo {
      width: 160px!important;
      height: 160px!important;
      left: 0!important;

      :deep(svg) {
        transform: scale(0.9) !important;
      }

    }

  }

}

.default-header-desktop {
  position: fixed;
  z-index: 999;

  box-sizing: border-box;

  width: 100%;
  max-width: 100%;
  height: 120px;

  transition: all 300ms ease-in-out;

  &__content {
    max-width: 1200px;
    margin: 0 auto;
  }

  &__nav {
    position: relative;
    display: flex;
    align-items: center;
    height: 120px;
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

.header {

  //.bg {
  //  position: absolute;
  //  top: 0;
  //  left: 0;
  //  width: 100vw;
  //  max-width: 100%;
  //  height: 120px;
  //  opacity: 0;
  //}

  .is-auth {
    display: flex;
    .header__nav--cart {
      margin-left: 10px;
      margin-right: 20px;
    }
  }

  &__nav {

    &--menu {
      display: flex;
      margin-left: 180px;

      &--item {
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

    &--phone {
      margin-left: auto;
      margin-right: auto;

      > a {
        position: relative;

        display: flex;
        align-items: center;

        font-family: Neucha, sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 19px;
        line-height: 21px;

        letter-spacing: 0.08em;

        color: #FFFFFF;
        cursor: pointer;

        > .icon {
          position: absolute;

          display: flex;
          justify-content: center;
          align-items: center;

          width: 45px;
          height: 45px;
          border-radius: 50%;

          background: #FFFFFF;
          box-shadow: 0 0 11px rgba(0, 0, 0, 0.6);
        }

        > span {
          display: block;
          padding-top: 3px;
          box-sizing: border-box;
        }

      }
    }

    &--history {
      margin-left: 12px;
      margin-right: 12px;
    }

    &--cart {
      position: relative;
      //margin-left: 12px;
      margin-right: 12px;
    }

    &--favorites {
      margin-left: 12px;
      margin-right: 12px;
      ::v-deep svg path {
        fill: #212121;
      }
    }

    &--avatar {
      //margin-left: 12px;
      border-radius: 50%;
      box-shadow: 9px 5px 37px rgba(0, 0, 0, 0.63);

      cursor: pointer;
    }

    &--profile {
      //margin-left: 12px;

      position: relative;
      padding-top: 7.5px;
      padding-bottom: 7.5px;
      box-sizing: border-box;

      > .login {
        display: flex;
        justify-content: center;
        align-items: center;

        width: 102px;
        height: 45px;

        border: none;

        background: #FFFFFF;
        box-shadow: 9px 5px 37px rgba(0, 0, 0, 0.63);
        border-radius: 36px;

        font-family: Neucha, sans-serif;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 18px;
        text-decoration: none;
        letter-spacing: 0.07em;
        color: #000000;

        //cursor: no-drop;
        cursor: pointer;

      }
    }

  }

}
</style>
