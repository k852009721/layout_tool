<template>
  <div id="richMenu" :class="previewSize">
    <div class="preview" :class="previewSize">
      <img class="background" src="" alt="" />
      <div class="top" :class="previewSize">
        <div class="top_border">
          <RichMenuBorderTop :icon-number="iconNumber"></RichMenuBorderTop>
        </div>
      </div>
      <div class="bottom" :class="previewSize">
        <div class="bottom_border">
          <RichMenuBorderBottom :icon-number="iconNumber"></RichMenuBorderBottom>
        </div>
      </div>
      <img class="avatar" :class="previewSize" :src="avatar" alt="">
      <div class="name" :class="previewSize">{{shopName}}</div>
      <div class="icons" :class="previewSize">
        <MenuIcon
          v-for="(icon, index) in iconArr"
          :key="index"
          :icon-type="icon"
          :icon-number="iconNumber"
        ></MenuIcon>
      </div>
      <IconBorder :icon-number="iconNumber"></IconBorder>
      <SettingIcon :icon-number="iconNumber"></SettingIcon>
    </div>
  </div>
</template>

<script>
import RichMenuBorderTop from "@/components/svg/richMenuBorderTop.vue";
import RichMenuBorderBottom from "@/components/svg/richMenuBorderBottom.vue";
import MenuIcon from "@/components/svg/menuIcon.vue";
import IconBorder from "@/components/svg/iconBorder.vue";
import SettingIcon from "@/components/svg/settingIcon.vue";

export default {
  name: "RichMenu",
  components: {
    RichMenuBorderTop,
    RichMenuBorderBottom,
    MenuIcon,
    IconBorder,
    SettingIcon,
  },
  props: {
    msg: String,
    richMenuData: Object,
    shopName: String
  },
  data() {
    return {
      avatar: require(`@/assets/images/default_avatar.png`),
      // iconArr: this.richMenuData.iconArr,
      // iconNumber: this.richMenuData.iconNumber,
    };
  },
  computed: {
    previewSize: function() {
      let size = ''
      this.iconNumber === 4
      ? size = 'small'
      : size = 'large'
      return size
    },
    iconArr: function() {
      return this.richMenuData.iconArr
    },
    iconNumber: function() {
      return this.richMenuData.iconNumber
    }
  },
};
</script>