<template>
  <div class="navbar">
    <div class="navfullwidth">
      <div class="navlogobox">
        <img :src="logo" :alt="sitename">
        <!-- sitename  logo param -->
        <span class="acn-sitename textfont">{{ sitename }}</span>
      </div>
      <div class="fullwidthmenus">
        <div v-for="menu in menus" :key="menu.id" class="menuitem textfont">{{ menu.text }}</div>
      </div>

    </div>
    <!-- mobile nav -->
    <!-- <transition name="mobliemenus">
      <div v-show="displaymenu" class="mobilemenu">
        <div v-for="menu in menus" :key="menu.id" class="menuitem textfont">{{ menu.text }}</div>
      </div>
    </transition> -->
  </div>

</template>




<script>
export default {
  name: "newnav",
  props: {
    navData: Object

  },

  data () {
    return {
      logo: this.navData.logo,
      sitename: this.navData.sitename,
      menus: this.navData.menus,
      menuname: this.navData.menuname,
      menuicon: this.navData.menuicon,
      displaymenu: false
    }
  },
  computed: {

 },
  methods: {
    make_menu () {
      this.displaymenu = !this.displaymenu
    }
  },
  mounted () {

  },
  updated () {

  }
}
</script>

<style scoped>
  .navbar {
    width: 100%;
    height: 85px;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 1000;
    background: #fff1f1;
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
    line-height: 85px;
    justify-content: space-between;
    box-shadow: 0 0 1px black;
  }
  .navfullwidth {
    width: 1920px;
    height: 100%;
    margin-left: auto;
    margin-right: auto;
    display: flex;
    flex-flow: row nowrap;
    justify-content: space-between;
  }
  .fullwidthmenus {
    display: flex;
    flex-direction: row;
    flex-wrap: nowrap;
  }
  .navlogobox {
    width: 180px;
    height: 100%;
    margin-left: 15px;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
  }
  .acn-sitename {
    margin: 0 20px;
  }
  .menuitem {
    margin: 0 30px;
  }
  .textfont {
    font-size:20px;
    font-family:PingFangSC-Medium,PingFang SC;
    font-weight:500;
    color:rgba(51,51,51,1);
  }
  .menuicon img {
      position: absolute;
      top: 20px;
      right: 20px;
      width: 40px;
      height:40px;
  }
  .menuicon {
      display: none;
  }
  .mobilemenu {
    display: none;
  }
  @media (max-width:900px) {
    .menuicon {
      display: block;
    }
    .fullwidthmenus {
      width: 100%;
      background: #fff1f1;
      height: 60px;
      position: fixed;
      left: 0;
      bottom: 0;
      display: flex;
      justify-content: space-between;
    }
    .mobilemenu {
      background: #fff1f1;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: center;
      width: 100%;
      position: fixed;
      top: 75px;
      z-index: 900;
    }
    .menuitem {
      font-size:12px;
      font-family:PingFangSC-Medium,PingFang SC;
      line-height: 60px;
      font-weight:500;
      color:rgba(51,51,51,1);
      margin: 0 10px;
    }
  }

  .mobilemenus-enter-active,
  .mobilemenus-leave-active {
    transition: all 3s ease-out;
  }
  .mobilemenus-enter,
  .mobilemenus-leave-active {
    transform: translateX(-100%);

  }
</style>
