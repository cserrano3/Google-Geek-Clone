<template>
    <div class="grid">
        <masonry
          :cols="{default: 3, 420: 1}"
          :gutter="10">
            <app-grid-item
                v-for="item in items"
                :content="item"
                :key="item.title"
                :openModal="openModal"
               >
            </app-grid-item>

        </masonry>
    </div>
</template>
<script>
import Vue from 'vue';
import VueMasonry from 'vue-masonry-css';
import GridItem from '../GridItem/GridItem.vue';
Vue.use(VueMasonry);
export default {
    name: 'app-grid',
    components: {
        'app-grid-item': GridItem
    },
    props: {
        items: {
            type: Array,
        },
        openModal: {
            type: Function
        }
    },
}
</script>
<style>
    .app-box {
        height: 200px;
    }
</style>
