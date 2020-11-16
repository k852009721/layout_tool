<template>
    <div id="mainWrapper">
        <div></div>
        <!-- <Layout></Layout> -->
        <div id="allSample">
            <div v-for="sample in samples"
            :key="sample.name"
            class="miniSample">
                <router-link :to="{name: 'Sample', params: {id: sample.id}}">
                    <div>{{sample.name}}</div>
                    <img :src="require(`@/assets/images/${sample.image}`)" alt="">
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
// import Layout from '@/views/Layout.vue'
import store from '@/store.js'

export default {
    name: "Index",
    components: {
        // Layout
    },
    data () {
        return {
            samples: store.samples
        }
    },
    methods: {

    },
}
</script>