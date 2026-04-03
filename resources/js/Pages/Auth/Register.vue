<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue';
import RegisterForm from '@/Components/RegisterForm.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <GuestLayout>
        <Head title="Register" />
        <RegisterForm />
    </GuestLayout>
</template>
