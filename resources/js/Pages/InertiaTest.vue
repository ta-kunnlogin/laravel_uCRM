<script setup>
    import { Link } from '@inertiajs/inertia-vue3';
    import { ref } from 'vue';

    const newTitle = ref();
    const newContent = ref();

</script>
<template>
    Inertiaテストです。
    <a href="/">aタグ経由です。</a>
    <Link href="/">Link経由です。</Link>
    <Link :href="route('inertia.index')">名前付きルートの確認です。</Link>
    <Link :href="route('inertia.show', {id: 50 })">ルートパラメータテストです。</Link>

    <div class="mb-8"></div>
    <input type="text" name="newTitle" v-model="newTitle"><br>
    <input type="text" name="newContent" v-model="newContent"><br>
    <Link as="button" method="post" :href="route('inertia.store')" :data="{
        title: newTitle,
        content: newContent,
    }">DB保存テスト</Link>

</template>