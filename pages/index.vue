<template>
  <div class="container">
    <newnav :nav-data="navData" />

  </div>
</template>

<script>
import Newnav from '~/components/Newnav.vue'
export default {
  data: function() {
    return {
      navData: {
        logo: "/favicon.ico",
        sitename: "营财宝",
        menus: [
          { id: 1, text: "公司注册" },
          { id: 2, text: "代理记账" },
          { id: 3, text: "商标服务" },
          { id: 4, text: "关于我们" }
        ],
        menuicon: "/menu2x.png",
        menuname: "菜单"
      }
    }
  },
  components: {
    Newnav
  }
}
</script>

<style scoped>
/* .container {
  width: 1920px;
  height: 500px;
  margin-left: auto;
  margin-right: auto;
}
@media (max-width: 900px) {
  .container {
    width: 750px;
    height: 500px;
    margin-left: auto;
    margin-right: auto;
  }


} */

</style>
