<template>
  <div class="burger-container">
    <div id="burger">
      <div class="bar topBar"></div>
      <div class="bar btmBar"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BurgerIcon"
};
</script>

<style lang="scss">
.hidden-checkbox {
  &:checked + .header--nav-strip {
    .burger-container {
      transform: rotate(90deg);
      #burger {
        .bar {
          transition: all 0.4s cubic-bezier(0.4, 0.01, 0.165, 0.99);
          transition-delay: 0.2s;
          &.topBar {
            transform: translateY(4px) rotate(45deg);
          }
          &.btmBar {
            transform: translateY(3px) rotate(-45deg);
          }
        }
      }
    }
  }
}

.burger-container {
  position: relative;
  display: flex;
  align-items: center;
  height: 50px;
  cursor: pointer;
  transform: rotate(0deg);
  transition: all 0.3s cubic-bezier(0.4, 0.01, 0.165, 0.99);
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  #burger {
    width: 18px;
    height: 8px;
    position: relative;
    display: block;
    .bar {
      width: 100%;
      height: 1px;
      display: block;
      position: relative;
      background: #000;
      transition: all 0.3s cubic-bezier(0.4, 0.01, 0.165, 0.99);
      transition-delay: 0s;
      @media(prefers-color-scheme: dark) {
        background: #fff;
      }
      &.topBar {
        transform: translateY(0px) rotate(0deg);
      }
      &.btmBar {
        transform: translateY(6px) rotate(0deg);
      }
    }
  }
}
</style>