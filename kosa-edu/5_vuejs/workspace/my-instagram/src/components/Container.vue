<template>
    <div v-if="step == 0">
        <!--postdata[i] -->
        <Post :postdata="p" v-for="(p, i) in postdata" :key="i" />
        <!-- <Post :postdata="postdata[1]" />
   <Post :postdata="postdata[2]" /> -->
    </div>

    <!-- 필터선택페이지 -->
    <div v-if="step == 1">
        <div class="upload-image"></div>
        <div class="filter-1"></div>
        <div class="filter-2"></div>
        <div class="filter-3"></div>
        <div class="filter-4"></div>
        <div class="filter-5"></div>
    </div>
</template>

<script>
    import Post from './Post.vue';

    export default {
        name: 'Cotainer',
        props: {
            postdata: Array,
            step: Number,
        },
        components: {
            Post,
        }
    };
</script>

<style>
    .upload-image {
        width: 100%;
        height: 450px;
        background: cornflowerblue;
        background-size: cover;
    }

    .filters {
        overflow-x: scroll;
        white-space: nowrap;
    }

    .filter-1 {
        width: 100px;
        height: 100px;
        background-color: cornflowerblue;
        margin: 10px 10px 10px auto;
        padding: 8px;
        display: inline-block;
        color: white;
        background-size: cover;
    }

    .filters::-webkit-scrollbar {
        height: 5px;
    }

    .filters::-webkit-scrollbar-track {
        background: #f1f1f1;
    }

    .filters::-webkit-scrollbar-thumb {
        background: #888;
        border-radius: 5px;
    }

    .filters::-webkit-scrollbar-thumb:hover {
        background: #555;
    }

    .write-box {
        border: none;
        width: 90%;
        height: 100px;
        padding: 15px;
        margin: auto;
        display: block;
        outline: none;
    }
</style>