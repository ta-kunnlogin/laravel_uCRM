<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head, Link } from '@inertiajs/vue3';
import FlashMessage from '@/Components/FlashMessage.vue';
import  Pagination from '@/Components/Pagination.vue';
// import { onMounted } from 'vue';

defineProps({
    customers: Object
})


</script>

<template>
        <ul v-for="customer in customers.data" :key="customer.id">
            <li>{{ customer.id }}</li>
            <li>{{ customer.name }}</li>
        </ul>
        <Pagination class="mt-6" :links="customers.links"></Pagination> 
</template>