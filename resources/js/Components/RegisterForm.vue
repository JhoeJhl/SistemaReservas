<script setup>
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { useForm, Link } from '@inertiajs/vue3';

const form = useForm({
    name: '',
    email: '',
    password: '',
    password_confirmation: '',
});

const submit = () => {
    form.post(route('register'), {
        onFinish: () => form.reset('password', 'password_confirmation'),
    });
};
</script>

<template>
    <form @submit.prevent="submit" class="space-y-4">
        <div>
            <InputLabel for="name" value="Nombre del Negocio" class="text-gray-700 dark:text-gray-300 font-medium mb-1.5" />
            <div class="relative group">
                <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-gray-400 group-focus-within:text-indigo-500 transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 21v-7.5a.75.75 0 0 1 .75-.75h3a.75.75 0 0 1 .75.75V21m-10.5 0v-7.5a.75.75 0 0 1 .75-.75h3a.75.75 0 0 1 .75.75V21m-4.5-16.5H21" />
                    </svg>
                </div>
                <TextInput
                    id="name"
                    type="text"
                    class="block w-full pl-11 py-3 bg-gray-50 dark:bg-gray-900 border-gray-200 dark:border-gray-800 rounded-xl focus:ring-indigo-500 focus:border-indigo-500 transition-all shadow-sm"
                    v-model="form.name"
                    required
                    autofocus
                    placeholder="Ej. Barbería Central"
                    autocomplete="name"
                />
            </div>
            <InputError class="mt-2" :message="form.errors.name" />
        </div>

        <div>
            <InputLabel for="email" value="Correo Electrónico" class="text-gray-700 dark:text-gray-300 font-medium mb-1.5" />
            <div class="relative group">
                <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-gray-400 group-focus-within:text-indigo-500 transition-colors">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 0 1-2.25 2.25h-15a2.25 2.25 0 0 1-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25m19.5 0v.243a2.25 2.25 0 0 1-1.07 1.916l-7.5 4.615a2.25 2.25 0 0 1-2.36 0L3.32 8.91a2.25 2.25 0 0 1-1.07-1.916V6.75" />
                    </svg>
                </div>
                <TextInput
                    id="email"
                    type="email"
                    class="block w-full pl-11 py-3 bg-gray-50 dark:bg-gray-900 border-gray-200 dark:border-gray-800 rounded-xl focus:ring-indigo-500 focus:border-indigo-500 transition-all shadow-sm"
                    v-model="form.email"
                    required
                    placeholder="hola@tu-negocio.com"
                    autocomplete="username"
                />
            </div>
            <InputError class="mt-2" :message="form.errors.email" />
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div>
                <InputLabel for="password" value="Contraseña" class="text-gray-700 dark:text-gray-300 font-medium mb-1.5" />
                <TextInput
                    id="password"
                    type="password"
                    class="block w-full py-3 bg-gray-50 dark:bg-gray-900 border-gray-200 dark:border-gray-800 rounded-xl focus:ring-indigo-500 focus:border-indigo-500 transition-all shadow-sm"
                    v-model="form.password"
                    required
                    placeholder="••••••••"
                    autocomplete="new-password"
                />
                <InputError class="mt-2" :message="form.errors.password" />
            </div>

            <div>
                <InputLabel for="password_confirmation" value="Confirmar" class="text-gray-700 dark:text-gray-300 font-medium mb-1.5" />
                <TextInput
                    id="password_confirmation"
                    type="password"
                    class="block w-full py-3 bg-gray-50 dark:bg-gray-900 border-gray-200 dark:border-gray-800 rounded-xl focus:ring-indigo-500 focus:border-indigo-500 transition-all shadow-sm"
                    v-model="form.password_confirmation"
                    required
                    placeholder="••••••••"
                    autocomplete="new-password"
                />
                <InputError class="mt-2" :message="form.errors.password_confirmation" />
            </div>
        </div>

        <PrimaryButton
            class="w-full justify-center mt-4 py-3.5 bg-indigo-600 hover:bg-indigo-700 active:bg-indigo-800 rounded-xl shadow-lg shadow-indigo-200 dark:shadow-none text-base font-bold transition-all transform active:scale-[0.98]"
            :class="{ 'opacity-25': form.processing }"
            :disabled="form.processing"
        >
            Crear cuenta gratuita
        </PrimaryButton>
    </form>
</template>
