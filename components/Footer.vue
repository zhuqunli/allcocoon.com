<template>
  <div class="acn-footer">
    <div class="container">
      <div class="left">
        <div v-for="local in locals" :key="local.id">
          <div class="textfont">
            {{ local.city }} : {{ local.company }}
          </div>
        </div>
        </div>

        <div class="right">
          <div v-for="qrcode in qrcodes" :key="qrcode.id" class="qrcodecls">
            <img :src="qrcode.url" :alt="qrcode.name">
            <div class="textfont">
               {{ qrcode.name }}
            </div>
          </div>
        </div>

    </div>
    <div class="sitecopyright textfont">
      <strong>CopyRight &copy {{ siteYear }} {{ sitecopys.company }} || {{ sitecopys.icp }}</strong>
    </div>
  </div>
</template>
<script>
export default {
  name: "Foot",
  props: {
    footerData: Object
  },
  data () {
    return {
      locals: this.footerData.locals,
      qrcodes: this.footerData.qrcodes,
      sitecopys: this.footerData.sitecopys,
      siteYear: new Date().getFullYear()

    }
  }
}
</script>
<style scoped>
.acn-footer {
  width: 100%;
  background: #fff1f1;
  position: fixed;
  bottom: 0;
}
.container {
  width: 1920px;
  height: 360px;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;

}
.sitecopyright {
  height: 100px;
  width: 1920px;
  margin: 0 auto;
  text-align: center;
  text-decoration: underline;
}

.left {
  width: 60%;
  display: flex;
  flex-direction: column;
  margin: auto 0;
}
.right {
  width: 40%;
  margin: auto 0;
  display: flex;
  flex-direction: row;

}
.textfont {
  font-size:24px;
  font-family:PingFangSC-Regular,PingFang SC;
  font-weight:400;
  color: black;
  line-height:50px;
}
.qrcodecls {
  margin: 0 50px;
}

@media (max-width:900px) {
  .ac-footer {
    display: none;
  }
  .container {
    display: none;
  }
  .sitecopyright {
    display: none;
  }
}

</style>
