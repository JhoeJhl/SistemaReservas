<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue';
import LoginForm from '@/Components/LoginForm.vue';
import { Head } from '@inertiajs/vue3';

defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});
</script>

<template>
    <GuestLayout>
        <Head title="Log in" />
        <LoginForm :can-reset-password="canResetPassword" :status="status" />
    </GuestLayout>
</template>
