<template>
    <div class="icon_border">
        <svg v-if="iconNumber === 6" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="1686" viewBox="0 0 2500 1686">
            <defs>
                <clipPath id="clip-Andy-richmenu_3.0_1_">
                <rect width="2500" height="1686"/>
                </clipPath>
            </defs>
            <g id="Andy-richmenu_3.0_1_" data-name="Andy-richmenu 3.0 – 1 " clip-path="url(#clip-Andy-richmenu_3.0_1_)">
                <line id="Line_3" data-name="Line 3" y2="774.189" transform="translate(857 714.492)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_4" data-name="Line 4" y2="774.189" transform="translate(1644 714.492)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_5" data-name="Line 5" x2="480" transform="translate(1010.5 1101.589)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_6" data-name="Line 6" x2="480" transform="translate(1797.24 1101.589)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_30" data-name="Line 30" x2="480" transform="translate(230.5 1102)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
            </g>
        </svg>
        <svg v-else-if="iconNumber === 8" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="2500" height="1686" viewBox="0 0 2500 1686">
            <defs>
                <clipPath id="clip-Andy-richmenu_3.0_1_1">
                <rect width="2500" height="1686"/>
                </clipPath>
            </defs>
            <g id="Andy-richmenu_3.0_1_1" data-name="Andy-richmenu 3.0 – 1 – 1" clip-path="url(#clip-Andy-richmenu_3.0_1_1)">
                <line id="Line_3" data-name="Line 3" y2="774.189" transform="translate(675.411 714.49)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_4" data-name="Line 4" y2="774.189" transform="translate(1250.5 714.49)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_5" data-name="Line 5" x2="375" transform="translate(775.5 1101.5)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_6" data-name="Line 6" x2="375" transform="translate(1351.24 1101.59)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_30" data-name="Line 30" x2="375" transform="translate(200.5 1101.59)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_31" data-name="Line 31" y2="774.189" transform="translate(1826.941 714.49)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
                <line id="Line_32" data-name="Line 32" x2="375" transform="translate(1927.24 1101.59)" fill="none" stroke="#000" stroke-width="1" opacity="0.6"/>
            </g>
        </svg>
        <svg v-else></svg>
    </div>
</template>

<script>
export default {
    props: {
        iconNumber: Number,
    }
}
</script>