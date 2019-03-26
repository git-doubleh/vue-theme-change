<template>
  <div class="home">
    <div class="body">
      <div class="div"></div>
      <span class="text">颜色改变</span>
    </div>
    <select
      name=""
      id=""
      @change="toggleBg($event)"
    >
      <option value="theme1">红</option>
      <option value="theme2">黑</option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'home',
  components: {
  },
  methods: {
    toggleBg (e) {
      window.document.documentElement.setAttribute('data-theme', e.target.value)
    }
  }
}
</script>
<style lang="scss" scoped>

@import '../assets/mixin.scss';
@import '../assets/variable.scss';
.home {
  width: 100%;
  .body {
    @include setbgColor('bg');
    height: 100px;
    .div{
      @include setbgColor('bg-sec');
      @include border($theme1-border);
      width: 50px;
      height: 50px;
    }
    .text{
      @include setFontColor('fc-main');
    }
  }
}
</style>

