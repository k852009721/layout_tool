<template>
  <div id="sample">
    <router-link to="/">
      <div class="btn back">重選樣板</div>
    </router-link>
    <div class="previewWrapper" :class="previewSize">
      <div id="preview" :style="`transform: scale(${transformScaleValue})`">
        <img class="background" src="" alt="" />
        <div class="wrapperTop" :style="sample.wrapperStyle.top">
          <img class="avatar" :src="avatar" :class="sample.avatar.position" />
          <div
            class="shopName"
            :style="sample.textStyle"
            :class="sample.textStyle.position"
          >
            {{ shopName }}
          </div>
          <div class="background"></div>
          <AvatarBorder
            v-if="sample.isAvatarBorder"
            :avatarBorderId="sampleId"
          ></AvatarBorder>
        </div>
        <div class="wrapperBottom" :style="sample.wrapperStyle.bottom">
          <Menu v-if="sample.isMenu" :menuId="sampleId"></Menu>
          <MenuBorder
            v-if="sample.isMenuBorder"
            :menuBorderId="sampleId"
          ></MenuBorder>
        </div>
        <div class="mask" :style="sample.maskStyle"></div>
      </div>
    </div>
    <RichMenu :rich-menu-data="richMenuData" :shop-name="shopName"></RichMenu>
    <div class="btn" @click="menuSetting">編輯圖片</div>
    <div id="setting_menu">
      <h3>基本資料</h3>
      <div class="setting">
        <div class="title">店家頭圖：</div>
        <div @click="triggerInput">選擇檔案</div>
        <input
          type="file"
          accept="image/gif,image/jpeg,image/jpg,image/png"
          class="value image"
          @change="changeImage($event)"
          data-type="avatar"
        />
      </div>
      <div class="setting">
        <div class="title">輸入店名：</div>
        <input type="text" class="value" @input="changeShopName($event)" />
      </div>
      <h3>底色or底圖設定</h3>
      <div class="setting">
        <div class="title">上傳底圖</div>
        <div @click="triggerInput">選擇檔案</div>
        <input
          type="file"
          accept="image/gif,image/jpeg,image/jpg,image/png"
          class="value image"
          @change="changeImage($event)"
          data-type="background"
        />
      </div>
      <div class="setting">
        <div class="title">上半部顏色</div>
        <span>頭</span>
        <input
          type="color"
          class="value start"
          @input="changeWrapper"
          :value="sample.wrapperStyle.top.backgroundColor"
          data-type="wrapperTop"
        />
        <span>尾</span>
        <input
          type="color"
          class="value end"
          @input="changeWrapper"
          :value="sample.wrapperStyle.top.backgroundColor"
          data-type="wrapperTop"
        />
      </div>
      <div class="setting">
        <div class="title">下半部顏色</div>
        <input
          type="color"
          class="value"
          @input="changeWrapper"
          :value="sample.wrapperStyle.bottom.backgroundColor"
          data-type="wrapperBottom"
        />
      </div>
      <h3>文字與邊框</h3>
      <div class="setting">
        <div class="title">頭像外框顏色：</div>
        <input type="color" class="value" @input="changeAvatarColor" />
      </div>
      <div class="setting">
        <div class="title">店名顏色：</div>
        <input
          type="color"
          class="value"
          @input="changeShopColor"
          :value="sample.textStyle.color"
        />
      </div>
      <div class="setting">
        <div class="title">選單文字顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="text"
        />
      </div>
      <div class="setting">
        <div class="title">選單外框顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="border"
        />
      </div>
      <h3>頂部遮色片</h3>
      <div class="setting">
        <div class="title">是否顯示</div>
        <select name="" id="maskHandle" @change="maskHandle">
          <option value="show">顯示</option>
          <option value="noshow">不顯示</option>
        </select>
      </div>
      <h2>圖2設定</h2>
      <div class="setting">
        <div class="title">項目數</div>
        <select name="" id="menuIconHandle" @change="menuIconHandle">
          <option value="4">4個</option>
          <option value="6">6個</option>
          <option value="8">8個</option>
        </select>
      </div>
      <div v-show="richMenuData.iconNumber === 6">5-6項內容:</div>
      <div v-show="richMenuData.iconNumber === 6" class="setting iconSelect">
        <select name="icon5" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 5">{{icon.content}}</option>
        </select>
        <select name="icon6" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 6">{{icon.content}}</option>
        </select>
      </div>
      <div v-show="richMenuData.iconNumber === 8">5-8項內容:</div>
      <div v-show="richMenuData.iconNumber === 8" class="setting iconSelect">
        <select name="icon5" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 5">{{icon.content}}</option>
        </select>
        <select name="icon6" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 6">{{icon.content}}</option>
        </select>
        <select name="icon7" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 7">{{icon.content}}</option>
        </select>
        <select name="icon8" @change="pickIcon">
          <option v-for="(icon,index) in menuIcons" :key="index" :value="icon.id" :selected="icon.id === 8">{{icon.content}}</option>
        </select>
      </div>
      <div class="setting">
        <div class="title">店名顏色：</div>
        <input
          type="color"
          class="value"
          @input="changeShopColor"
          :value="'#776651'"
          data-type="richmenu"
        />
      </div>
      <h3>底色or底圖設定</h3>
      <div class="setting">
        <div class="title">上傳底圖</div>
        <div @click="triggerInput">選擇檔案</div>
        <input
          type="file"
          accept="image/gif,image/jpeg,image/jpg,image/png"
          class="value image"
          @change="changeImage($event)"
          data-type="richBackground"
        />
      </div>
      <div class="setting">
        <div class="title">上半部顏色</div>
        <input
          type="color"
          class="value start"
          @input="changeWrapper"
          :value="sample.wrapperStyle.top.backgroundColor"
          data-type="richWrapperTop"
        />
      </div>
      <div class="setting">
        <div class="title">下半部顏色</div>
        <input
          type="color"
          class="value"
          @input="changeWrapper"
          :value="sample.wrapperStyle.bottom.backgroundColor"
          data-type="richWrapperBottom"
        />
      </div>
      <h3>按鈕與邊框</h3>
      <div class="setting">
        <div class="title">上外框顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="borderTop"
        />
      </div>
      <div class="setting">
        <div class="title">下外框顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="borderBottom"
        />
      </div>
      <div class="setting">
        <div class="title">按鈕顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="settingIcon"
        />
      </div>
      <div class="setting">
        <div class="title">選項文字顏色：</div>
        <input
          type="color"
          class="value"
          @input="richMenuSVGcolor"
          :value="sample.menuStyle.color"
          data-type="richIcon"
        />
      </div>
    </div>
    <div id="convertImage" @click="convertImage" class="btn">產生圖片</div>
    <div id="downloadImage" @click="downloadImage" class="btn">下載圖片</div>

    <div id="finalImage"></div>
    <div id="finalImage2"></div>
  </div>
</template>
<script>
import Menu from "@/components/svg/menu.vue";
import RichMenu from "@/components/RichMenu.vue";
import AvatarBorder from "@/components/svg/avatarBorder.vue";
import MenuBorder from "@/components/svg/menuBorder.vue";
import * as htmlToImage from "html-to-image";
import download from "downloadjs";
import store from "@/store.js";
// import { toPng } from 'html-to-image';

export default {
  name: "Sample",
  components: {
    // HelloWorl
    Menu,
    AvatarBorder,
    MenuBorder,
    RichMenu,
  },
  data() {
    return {
      sampleId: +this.$route.params.id,
      avatar: require(`@/assets/images/default_avatar.png`),
      shopName: "SHOP NAME",
      maskStyle: {
        background: "linear-gradient(to bottom, #000000, #ffffff)",
      },
      transformScaleValue: "",
      previewSize: "large",
      richMenuData: {
        iconArr: [1, 2, 3, 4],
        iconNumber: 4,
      },
    };
  },
  computed: {
    sample() {
      return store.samples.find((sample) => sample.id === this.sampleId);
    },
    menuIcons() {
      return store.menuIcons
    },
  },
  methods: {
    changeImage(e) {
      const file = e.target.files[0];
      const reader = new FileReader();
      const type = e.target.dataset.type;

      let avatar = document.body.querySelectorAll("img.avatar");
      let background = document.body.querySelector("#preview .wrapperTop");
      let richBackgroundTop = document.body.querySelector("#richMenu .preview .top");

      reader.readAsDataURL(file);
      reader.onload = function () {
        switch (type) {
          case "avatar":
            avatar.forEach((img) => {
              img.src = this.result;
            });
            break;
          case "background":
            background.style.background = `url(${this.result})`
            break;
          case "richBackground":
            richBackgroundTop.style.background = `url(${this.result})`
            break;
        }
      };
    },
    changeShopName(e) {
      const newShopName = e.target.value;
      this.shopName = newShopName;
    },
    changeShopColor(e) {
      const newcolor = e.target.value;
      let title = document.body.querySelector("#preview .shopName");
      let richMenuTitle = document.body.querySelector("#richMenu .preview .name");
      e.target.dataset.type === 'richmenu'
      ? richMenuTitle.style.color = newcolor
      : title.style.color = newcolor
    },
    changeAvatarColor(e) {
      const newColor = e.target.value;

      let borderFill = document.body.querySelectorAll(
        "#avatarBorder svg [fill]"
      );
      let borderStroke = document.body.querySelectorAll(
        "#avatarBorder svg [stroke]"
      );

      borderFill.forEach((el) => {
        el.style.fill = newColor;
      });
      borderStroke.forEach((el) => {
        el.style.stroke = newColor;
      });
    },
    richMenuSVGcolor(e) {
      const newColor = e.target.value;
      const type = e.target.dataset.type;

      let textFill = document.body.querySelectorAll("#menu svg [fill]");
      let textStroke = document.body.querySelectorAll("#menu svg [stroke]");
      let borderFill = document.body.querySelectorAll(
        '#menuBorder svg [fill]:not([fill="none"])'
      );
      let borderStroke = document.body.querySelectorAll(
        '#menuBorder svg [stroke]:not([stroke="none"])'
      );
      let topBorder = document.body.querySelectorAll('#richMenu .preview .richMenuBorderTop svg line')
      let bottomBorder = document.body.querySelectorAll('#richMenu .preview .richMenuBorderBottom svg line')
      let settingIcon = document.body.querySelectorAll('#richMenu .preview .settingIcon svg [fill]:not([fill="none"]')

      let menuIconFill = document.body.querySelectorAll('#richMenu .preview .icons svg g')
      let menuIconStroke = document.body.querySelectorAll('#richMenu .preview .icons svg [Stroke]:not([Stroke="none"]')

      switch (type) {
        case "text":
          textFill.forEach((el) => {
            el.style.fill = newColor;
          });
          textStroke.forEach((el) => {
            el.style.stroke = newColor;
          });
          break;
        case "border":
          borderFill.forEach((el) => {
            el.style.fill = newColor;
          });
          borderStroke.forEach((el) => {
            el.style.stroke = newColor;
          });
          break;
        case 'borderTop':
          topBorder.forEach((el)=>{
            el.style.fill = newColor;
            el.style.stroke = newColor;
          })
          break;
        case 'borderBottom':
          bottomBorder.forEach((el)=>{
            el.style.fill = newColor;
            el.style.stroke = newColor;
          })
          break;
        case 'settingIcon':
          settingIcon.forEach((el)=>{
            el.style.fill = newColor;
          })
          break;
        case 'richIcon':
          menuIconFill.forEach((el)=>{
            el.style.fill = newColor;
          })
          menuIconStroke.forEach((el)=>{
            el.style.stroke = newColor;
          })
          // menuIconText.forEach((el)=>{
          //   el.style.fill = newColor;
          // })
          // menuIconPath.forEach((el)=>{
          //   el.style.fill = newColor;
          // })
          break;
      }
    },
    changeMaskColor(e) {
      const newMaskColor = e.target.value;
      this.maskStyle.background = `linear-gradient(to bottom, ${newMaskColor}, #ffffff)`;
    },
    changeWrapper(e) {
      const newColor = e.target.value;
      const type = e.target.dataset.type;

      let direction = "to top";
      let startColor = document.body.querySelector("input.value.start").value;
      let endColor = document.body.querySelector("input.value.end").value;

      switch (type) {
        case "wrapperTop":
          document.body.querySelector(
            "#preview .wrapperTop"
          ).style.background = `linear-gradient(${direction}, ${startColor}, ${endColor})`;
          break;
        case "wrapperBottom":
          document.body.querySelector(
            "#preview .wrapperBottom"
          ).style.backgroundColor = newColor;
          break;
        case "richWrapperTop":
          document.body.querySelector(
            "#richMenu .preview .top"
          ).style.backgroundColor = newColor;
          break;
        case "richWrapperBottom":
          document.body.querySelector(
            "#richMenu .preview .bottom"
          ).style.backgroundColor = newColor;
          break;
      }
    },
    convertImage() {
      let node = document.querySelector("#preview");
      let node2 = document.querySelector("#richMenu");

      htmlToImage
        .toPng(node)
        .then(function (dataUrl) {
          let img = new Image();
          img.src = dataUrl;
          document.getElementById("finalImage").appendChild(img);
          // download(dataUrl, 'my-node.png');
        })
        .catch(function (error) {
          console.error("oops, something went wrong!", error);
        });
      
      htmlToImage
        .toPng(node2)
        .then(function (dataUrl) {
          let img = new Image();
          img.src = dataUrl;
          document.getElementById("finalImage2").appendChild(img);
        })
        .catch(function (error) {
          console.error("oops, something went wrong!", error);
        });
    },
    downloadImage() {
      let node = document.body.querySelector("#preview");
      let newPreveiw = node.cloneNode(true);
      let wp = document.getElementById('finalImage');
      newPreveiw.style.transform = "unset"
      // newPreveiw.style.transformOrigin = "unset"

      wp.appendChild(newPreveiw)

      htmlToImage.toPng(document.body.querySelector('#finalImage #preview'))
      .then(function (dataUrl) {
        download(dataUrl, 'my-node.png');
  });
    },
    matchMedia() {
      window.matchMedia("(min-width: 1025px)").matches
        ? ((this.transformScaleValue = 1), (this.previewSize = "large"))
        : window.matchMedia("(min-width: 415px)").matches
        ? ((this.transformScaleValue = 0.5), (this.previewSize = "mid"))
        : ((this.transformScaleValue = 0.3), (this.previewSize = "small"));
    },
    triggerInput(e) {
      e.target.nextSibling.click();
    },
    maskHandle(e) {
      let mask = document.body.querySelector(".mask");

      e.target.value === "show"
        ? (mask.classList.add("show"), mask.classList.remove("noshow"))
        : (mask.classList.add("noshow"), mask.classList.remove("show"));
    },
    menuSetting() {
      let menuSetting = document.getElementById("setting_menu");
      menuSetting.classList.toggle("active");
    },
    richMenuSetting() {
      let menuSetting = document.getElementById("setting_rich");
      menuSetting.classList.toggle("active");
    },
    menuIconHandle(e) {
      let richMenuData = this.richMenuData;

      switch (e.target.value) {
        case '4':
          richMenuData.iconNumber = 4;
          break;
        case '6':
          richMenuData.iconNumber = 6;
          richMenuData.iconArr = [1,2,3,4,5,6];
          break;
        case '8':
          richMenuData.iconNumber = 8;
          richMenuData.iconArr = [1,2,3,4,5,6,7,8];
          break;
      }
    },
    pickIcon(e) {
      let richMenuData = this.richMenuData;
      let iconArr = richMenuData.iconArr
      let iconId = +e.target.value
      switch (e.target.name) {
        case 'icon5':
          iconArr.splice(4,1,iconId)
          break;
        case 'icon6':
          iconArr.splice(5,1,iconId)
          break;
        case 'icon7':
          iconArr.splice(6,1,iconId)
          break;
        case 'icon8':
          iconArr.splice(7,1,iconId)
          break;
      }
    },
  },
  mounted: function () {
    //scale preview
    new Promise((resolve) => {
      resolve(this.matchMedia());
    })
      // eslint-disable-next-line no-unused-vars
      .then((res) => (this.renderDone = true));

    window.onresize = () => {
      this.matchMedia();
    };

    //change menu color
    let svgFill = document.body.querySelectorAll("#menu svg [fill]");
    let svgStroke = document.body.querySelectorAll("#menu svg [stroke]");

    svgFill.forEach((el) => {
      el.style.fill = this.sample.menuStyle.color;
    });
    svgStroke.forEach((el) => {
      el.style.stroke = this.sample.menuStyle.color;
    });

    //move to top
    window.scrollTo(0, 0);
  },
};
</script>
