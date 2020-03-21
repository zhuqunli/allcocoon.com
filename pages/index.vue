<template>
  <div class="container">
    <navbar :nav-data="navData" />
    <!-- <newnav :nav-data="navData" /> -->
    <foot :footer-data="footerData" />
  </div>
</template>

<script>
import Newnav from '~/components/Newnav.vue'
import Foot from '~/components/Footer.vue'
import Navbar from '~/components/Navbar.vue'
export default {
  data: function() {
    return {
      navData: {
        logo: "/favicon.ico",
        sitename: "营财宝",
        menus: [
          { id: 1, text: "公司注册" },
          { id: 2, text: "代理记账" },
          { id: 3, text: "知识产权" },
          { id: 4, text: "商标服务" },
          { id: 5, text: "关于我们" }
        ],
        menuicon: "/menu2x.png",
        menuname: "菜单"
      },
      footerData: {
        locals:[
          { id: 1, city: "苏州", company: "皆茧苏州商务秘书有限公司"},
          { id: 2, city: "上海", company: "皆茧科技限公司"},
          { id: 3, city: "杭州", company: "来刻（苏州）科技有限公司"}
        ],
        qrcodes: [
          { id: 1, name:"客服微信", url:"/" },
          { id: 1, name:"关注微信公众号", url:"/" }
        ],
        sitecopys: {
          company: "皆茧科技有限公司",
          icp: "沪ICP备 19045206号-1"  // suzhou-icp: 苏ICP备 19031935号-1
        }

      }
    }
  },
  components: {
    Newnav,
    Foot,
    Navbar
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
