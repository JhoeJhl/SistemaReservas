<script setup>
import { Link } from '@inertiajs/vue3';
</script>

<template>
    <footer class="bg-white dark:bg-gray-950 border-t border-gray-100 dark:border-gray-800 transition-colors">
        <div class="mx-auto max-w-7xl px-4 py-16 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-12 mb-12">
                <div class="col-span-1 md:col-span-2">
                    <div class="flex items-center gap-2 mb-6">
                        <div class="flex h-9 w-9 items-center justify-center rounded-lg bg-indigo-600 text-white shadow-lg shadow-indigo-200 dark:shadow-none">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="h-5 w-5">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" />
                            </svg>
                        </div>
                        <span class="text-xl font-bold tracking-tight text-gray-900 dark:text-white">Reserva<span class="text-indigo-600 dark:text-indigo-400">Pro</span></span>
                    </div>
                    <p class="text-gray-600 dark:text-gray-400 max-w-sm leading-relaxed">Simplificando la gestión de servicios para negocios modernos en todo el mundo. Automatiza tu agenda y haz crecer tu marca.</p>
                </div>
                <div>
                    <h4 class="font-bold text-gray-900 dark:text-white mb-6 text-sm uppercase tracking-wider">Producto</h4>
                    <ul class="space-y-4 text-sm text-gray-600 dark:text-gray-400">
                        <li><a href="#soluciones" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Características</a></li>
                        <li><a href="#precios" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Precios</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-gray-900 dark:text-white mb-6 text-sm uppercase tracking-wider">Empresa</h4>
                    <ul class="space-y-4 text-sm text-gray-600 dark:text-gray-400">
                        <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Sobre nosotros</a></li>
                        <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Contacto</a></li>
                        <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Blog</a></li>
                    </ul>
                </div>
            </div>
            <div class="pt-8 border-t border-gray-100 dark:border-gray-800 flex flex-col md:flex-row justify-between items-center gap-4">
                <p class="text-sm text-gray-500 dark:text-gray-500">© 2026 EzReserv</p>
                <div class="flex space-x-8 text-sm">
                    <a href="#" class="text-gray-500 hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Privacidad</a>
                    <a href="#" class="text-gray-500 hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Términos</a>
                    <a href="#" class="text-gray-500 hover:text-indigo-600 dark:hover:text-indigo-400 transition-colors">Cookies</a>
                </div>
            </div>
        </div>
    </footer>
</template>
