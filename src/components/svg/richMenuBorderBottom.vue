<template>
<div class="richMenuBorderBottom">
  <svg v-if="iconNumber === 4"  xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="843" viewBox="0 0 2500 843">
  <defs>
    <clipPath id="clip-Andy-richmenu2.0">
      <rect width="2500" height="843"/>
    </clipPath>
  </defs>
  <g id="Andy-richmenu2.0" clip-path="url(#clip-Andy-richmenu2.0)">
    <g id="Group_5257" data-name="Group 5257" transform="translate(20.791 397)">
      <line id="Line_21" data-name="Line 21" y2="349.541" transform="translate(55.2 39.5)" fill="none" stroke="#776651" stroke-width="20"/>
      <line id="Line_22" data-name="Line 22" x2="2367.81" transform="translate(45.5 389.041)" fill="none" stroke="#776651" stroke-width="20"/>
      <line id="Line_23" data-name="Line 23" y2="358.541" transform="translate(2413.31 40.5)" fill="none" stroke="#776651" stroke-width="20"/>
    </g>
  </g>
  </svg>
  <svg v-else xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="1686" viewBox="0 0 2500 1686">
    <defs>
      <clipPath id="clip-Andy-richmenu_3.0_1_2">
        <rect width="2500" height="1686"/>
      </clipPath>
    </defs>
    <g id="Andy-richmenu_3.0_1_2" data-name="Andy-richmenu 3.0 – 1 – 2" clip-path="url(#clip-Andy-richmenu_3.0_1_2)">
      <g id="Group_5257" data-name="Group 5257" transform="translate(22.5 566.129)">
        <line id="Line_21" data-name="Line 21" y2="1031.975" transform="translate(54.5 39.871)" fill="none" stroke="#776651" stroke-width="20"/>
        <line id="Line_22" data-name="Line 22" x2="2366" transform="translate(45.5 1071.846)" fill="none" stroke="#776651" stroke-width="20"/>
        <line id="Line_23" data-name="Line 23" y2="1041.346" transform="translate(2411.5 40.5)" fill="none" stroke="#776651" stroke-width="20"/>
      </g>
    </g>
  </svg>
</div>
</template>

<script>
export default {
  props: {
    iconNumber: Number,
  }
}
</script>