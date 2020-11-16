<template>
  <div class="layout">
    <div id="preview">
      <div class="background"></div>
      <div class="topWrapper">
        <div class="avatar">
          <img class="avatarImg" src="" alt="">
        </div>
        <div class="shopName"></div>
      </div>
      <div class="bottomWrapper"></div>
    </div>
  </div>
</template>

<script>
// import Menu from '@/components/svg/menu.vue'

export default {
  name: "Layout",
  components: {
    // Menu
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
  },
};
</script>
