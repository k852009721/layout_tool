<template>
    <div class="settingIcon">
        <svg v-if="iconNumber === 4" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="843" viewBox="0 0 2500 843">
            <defs>
                <clipPath id="clip-Andy-richmenu2.0_1">
                <rect width="2500" height="843"/>
                </clipPath>
            </defs>
            <g id="Andy-richmenu2.0_1" data-name="Andy-richmenu2.0 – 1" clip-path="url(#clip-Andy-richmenu2.0_1)">
                <g id="baseline-settings-20px" transform="translate(2310 73)">
                <path id="Path_2223" data-name="Path 2223" d="M0,0H130V130H0Z" fill="none"/>
                <path id="Path_2224" data-name="Path 2224" d="M91.452,59.07A42.421,42.421,0,0,0,91.777,54a32.058,32.058,0,0,0-.39-5.07l10.985-8.58a2.686,2.686,0,0,0,.65-3.315l-10.4-18a2.643,2.643,0,0,0-3.185-1.17L76.5,23.06a38.082,38.082,0,0,0-8.775-5.07L65.777,4.21A2.6,2.6,0,0,0,63.177,2h-20.8a2.53,2.53,0,0,0-2.535,2.21l-1.95,13.78a39.1,39.1,0,0,0-8.775,5.07l-12.935-5.2A2.571,2.571,0,0,0,13,19.03l-10.4,18a2.519,2.519,0,0,0,.65,3.315l10.985,8.58a30.633,30.633,0,0,0-.065,10.14L3.182,67.65a2.686,2.686,0,0,0-.65,3.315l10.4,18.005a2.643,2.643,0,0,0,3.185,1.17l12.935-5.2a38.082,38.082,0,0,0,8.775,5.07l1.95,13.78a2.644,2.644,0,0,0,2.6,2.21h20.8a2.484,2.484,0,0,0,2.535-2.21l1.95-13.78a39.1,39.1,0,0,0,8.775-5.07l12.935,5.2a2.571,2.571,0,0,0,3.185-1.17l10.4-18.005a2.519,2.519,0,0,0-.65-3.315L91.452,59.07ZM52.777,73.5A19.5,19.5,0,1,1,72.277,54,19.557,19.557,0,0,1,52.777,73.5Z" transform="translate(12.223 11)" fill="#776651"/>
                </g>
                <g id="Group_5504" data-name="Group 5504" transform="translate(71 22115)">
                <path id="_007-add-group" data-name="007-add-group" d="M100,83.594H83.594V100H75.781V83.594H59.375V75.781H75.781V59.375h7.813V75.781H100ZM58.458,43.64a22.055,22.055,0,0,1-7.307,21.647c.137.054.275.107.411.163v8.633A29.3,29.3,0,0,0,37.5,70.508V70.5l-.2,0v0A29.526,29.526,0,0,0,7.813,100H0A37.363,37.363,0,0,1,22.994,65.551a22.066,22.066,0,0,1,18.15-38.776,22.023,22.023,0,1,1,35.532,12.2A36.822,36.822,0,0,1,92.751,51.367H82.234a29.369,29.369,0,0,0-18.022-7.382c-.518.037-1.04.056-1.566.056A22.018,22.018,0,0,1,58.458,43.64ZM48.438,22.021A14.208,14.208,0,1,0,62.646,7.813,14.224,14.224,0,0,0,48.438,22.021Zm2.734,26.417A14.258,14.258,0,1,0,36.914,62.7,14.274,14.274,0,0,0,51.172,48.438Zm0,0" transform="translate(16 -22027)" fill="#776651" stroke="#776651" stroke-width="2"/>
                </g>
            </g>
        </svg>
        <svg v-else xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="1686" viewBox="0 0 2500 1686">
            <defs>
                <clipPath id="clip-Andy-richmenu_3.0_1_">
                <rect width="2500" height="1686"/>
                </clipPath>
            </defs>
            <g id="Andy-richmenu_3.0_1_" data-name="Andy-richmenu 3.0 – 1 " clip-path="url(#clip-Andy-richmenu_3.0_1_)">
                <g id="baseline-settings-20px" transform="translate(2234 119)">
                <path id="Path_2223" data-name="Path 2223" d="M0,0H130V130H0Z" fill="none"/>
                <path id="Path_2224" data-name="Path 2224" d="M91.452,59.07A42.421,42.421,0,0,0,91.777,54a32.058,32.058,0,0,0-.39-5.07l10.985-8.58a2.686,2.686,0,0,0,.65-3.315l-10.4-18a2.643,2.643,0,0,0-3.185-1.17L76.5,23.06a38.082,38.082,0,0,0-8.775-5.07L65.777,4.21A2.6,2.6,0,0,0,63.177,2h-20.8a2.53,2.53,0,0,0-2.535,2.21l-1.95,13.78a39.1,39.1,0,0,0-8.775,5.07l-12.935-5.2A2.571,2.571,0,0,0,13,19.03l-10.4,18a2.519,2.519,0,0,0,.65,3.315l10.985,8.58a30.633,30.633,0,0,0-.065,10.14L3.182,67.65a2.686,2.686,0,0,0-.65,3.315l10.4,18.005a2.643,2.643,0,0,0,3.185,1.17l12.935-5.2a38.082,38.082,0,0,0,8.775,5.07l1.95,13.78a2.644,2.644,0,0,0,2.6,2.21h20.8a2.484,2.484,0,0,0,2.535-2.21l1.95-13.78a39.1,39.1,0,0,0,8.775-5.07l12.935,5.2a2.571,2.571,0,0,0,3.185-1.17l10.4-18.005a2.519,2.519,0,0,0-.65-3.315L91.452,59.07ZM52.777,73.5A19.5,19.5,0,1,1,72.277,54,19.557,19.557,0,0,1,52.777,73.5Z" transform="translate(12.223 11)" fill="#776651"/>
                </g>
                <g id="Group_5504" data-name="Group 5504" transform="translate(143 22158)">
                <path id="_007-add-group" data-name="007-add-group" d="M100,83.594H83.594V100H75.781V83.594H59.375V75.781H75.781V59.375h7.813V75.781H100ZM58.458,43.64a22.055,22.055,0,0,1-7.307,21.647c.137.054.275.107.411.163v8.633A29.3,29.3,0,0,0,37.5,70.508V70.5l-.2,0v0A29.526,29.526,0,0,0,7.813,100H0A37.363,37.363,0,0,1,22.994,65.551a22.066,22.066,0,0,1,18.15-38.776,22.023,22.023,0,1,1,35.532,12.2A36.822,36.822,0,0,1,92.751,51.367H82.234a29.369,29.369,0,0,0-18.022-7.382c-.518.037-1.04.056-1.566.056A22.018,22.018,0,0,1,58.458,43.64ZM48.438,22.021A14.208,14.208,0,1,0,62.646,7.813,14.224,14.224,0,0,0,48.438,22.021Zm2.734,26.417A14.258,14.258,0,1,0,36.914,62.7,14.274,14.274,0,0,0,51.172,48.438Zm0,0" transform="translate(16 -22027)" fill="#776651" stroke="#776651" stroke-width="2"/>
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