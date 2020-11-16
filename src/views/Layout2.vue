<template>
  <div class="layout">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div id="componentControl">
      <div class="avatarControl">
        <input
          type="file"
          accept="image/gif,image/jpeg,image/jpg,image/png"
          @change="changeImage($event)"
        />
      </div>
      <div class="shopNameControl">
        <input type="text" 
        @input="changeShopName($event)"
        placeholder="shopNameControl" />
      </div>
      <div class="textColorControl">
        <input type="color"
        @change="changeTextColor($event)"
        placeholder="textColorControl" />
      </div>
      <div class="backgroundControl">
        <input type="text" placeholder="backgroundControl" />
      </div>
      <div class="maskControl">
        <input type="color"
        @change="changeMaskColor($event)"
        placeholder="maskControl" />
      </div>
    </div>
    <div id="preview">
      <img class="" :src="layoutImg" alt="" />
      <img class="avatar" :src="avatar" />
      <div class="shopName">{{shopName}}</div>
      <div class="background"></div>
      <div class="mask" :style="maskStyle"></div>
      <Menu></Menu>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Menu from '@/components/svg/menu.vue'

export default {
  name: "Layout",
  components: {
    // HelloWorl
    Menu
  },
  data() {
    return {
      layoutImg: "/image/layout_2.png",
      avatar: require('../assets/images/default_avatar.png'),
      shopName: 'SHOP NAME',
      textColor: '#FFFFFF',
      maskStyle: {
        background: 'linear-gradient(to bottom, #000000, #ffffff)',
      },
    };
  },
  methods: {
    changeImage(e) {
      const file = e.target.files[0];
      const reader = new FileReader();
      const that = this;
      reader.readAsDataURL(file);
      reader.onload = function () {
        that.avatar = this.result;
      };
    },
    changeShopName(e) {
      const newShopName = e.target.value
      this.shopName = newShopName
    },
    changeTextColor(e) {
      const newTextColor = e.target.value
      document.body.querySelectorAll('#preview svg path').forEach((path)=>{
        path.style.fill = newTextColor
      })
      document.body.querySelectorAll('#preview svg line').forEach((line)=>{
        line.style.stroke = newTextColor
      })
      document.body.querySelectorAll('#preview svg text').forEach((text)=>{
        text.style.fill = newTextColor
      })
    },
    changeMaskColor(e) {
      const newMaskColor = e.target.value
      this.maskStyle.background = `linear-gradient(to bottom, ${newMaskColor}, #ffffff)`
    },
  },
};
</script>
