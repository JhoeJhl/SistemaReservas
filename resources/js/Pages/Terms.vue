<script setup>
import { Head, Link } from '@inertiajs/vue3';
import DarkModeToggle from '@/Components/DarkModeToggle.vue';
import Footer from '@/Components/Footer.vue';

const sections = [
  {
    title: '1. Aceptación de los Términos',
    content: 'Al acceder y utilizar ReservaPro, usted acepta cumplir y estar sujeto a estos Términos y Condiciones. Si no está de acuerdo con alguna parte de estos términos, no podrá utilizar nuestro servicio.'
  },
  {
    title: '2. Descripción del Servicio',
    content: 'ReservaPro es una plataforma SaaS que permite a los negocios gestionar citas, clientes y servicios. Actuamos como intermediarios tecnológicos entre el prestador del servicio y el cliente final.'
  },
  {
    title: '3. Registro y Seguridad',
    content: 'Usted es responsable de mantener la confidencialidad de sus credenciales de acceso. Cualquier actividad realizada bajo su cuenta será su responsabilidad. Debe notificarnos inmediatamente sobre cualquier uso no autorizado.'
  },
  {
    title: '4. Políticas de Reserva y Cancelación',
    content: 'Los negocios que utilizan nuestra plataforma son responsables de establecer sus propias políticas de cancelación y reembolso. ReservaPro proporciona las herramientas para gestionar estas políticas pero no interviene en disputas entre el negocio y sus clientes.'
  },
  {
    title: '5. Pagos y Suscripciones',
    content: 'El uso de las funciones avanzadas de ReservaPro requiere una suscripción activa. Los pagos se procesan de forma segura. La falta de pago puede resultar en la suspensión temporal o definitiva del servicio.'
  },
  {
    title: '6. Protección de Datos (Privacidad)',
    content: 'Nos tomamos en serio su privacidad. El manejo de los datos personales de sus clientes debe cumplir con las normativas locales (como GDPR). Usted es el responsable del tratamiento de los datos de sus clientes captados a través de nuestra plataforma.'
  },
  {
    title: '7. Limitación de Responsabilidad',
    content: 'ReservaPro no se hace responsable por pérdidas de ingresos debidas a interrupciones del servicio, errores en las reservas o ausencias de clientes (no-shows).'
  }
];
</script>

<template>
    <Head title="Términos y Condiciones - ReservaPro" />

    <div class="min-h-screen bg-white dark:bg-gray-950 text-gray-900 dark:text-gray-100 transition-colors duration-300">
        <!-- Simple Nav -->
        <nav class="border-b border-gray-100 dark:border-gray-800 bg-white/80 dark:bg-gray-950/80 backdrop-blur-md sticky top-0 z-50">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="flex h-16 items-center justify-between">
                    <Link href="/" class="flex items-center gap-2">
                        <div class="flex h-8 w-8 items-center justify-center rounded-lg bg-indigo-600 text-white">
                            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="h-5 w-5">
                                <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" />
                            </svg>
                        </div>
                        <span class="text-xl font-bold tracking-tight">Reserva<span class="text-indigo-600">Pro</span></span>
                    </Link>
                    <DarkModeToggle />
                </div>
            </div>
        </nav>

        <header class="py-16 bg-gray-50 dark:bg-gray-900/50 border-b border-gray-100 dark:border-gray-800">
            <div class="mx-auto max-w-3xl px-4 text-center">
                <h1 class="text-4xl font-extrabold tracking-tight sm:text-5xl mb-4">Términos y Condiciones</h1>
                <p class="text-lg text-gray-600 dark:text-gray-400">Última actualización: 3 de abril de 2026</p>
            </div>
        </header>

        <main class="py-16">
            <div class="mx-auto max-w-3xl px-4">
                <div class="prose prose-indigo dark:prose-invert max-w-none">
                    <p class="text-lg leading-relaxed mb-12">
                        Bienvenido a ReservaPro. Estos términos rigen el uso de nuestra plataforma y servicios. Al utilizar nuestro sistema, usted acepta estas condiciones en su totalidad.
                    </p>

                    <div v-for="section in sections" :key="section.title" class="mb-10">
                        <h2 class="text-2xl font-bold mb-4 text-gray-900 dark:text-white">{{ section.title }}</h2>
                        <p class="text-gray-600 dark:text-gray-400 leading-relaxed">
                            {{ section.content }}
                        </p>
                    </div>

                    <div class="mt-16 p-8 bg-indigo-50 dark:bg-indigo-900/20 rounded-3xl border border-indigo-100 dark:border-indigo-800">
                        <h3 class="text-xl font-bold mb-2">¿Tiene dudas?</h3>
                        <p class="text-gray-600 dark:text-gray-400 mb-4">Si tiene alguna pregunta sobre estos términos, no dude en contactarnos.</p>
                        <a href="mailto:soporte@reservapro.com" class="text-indigo-600 dark:text-indigo-400 font-bold hover:underline">soporte@reservapro.com</a>
                    </div>
                </div>
            </div>
        </main>

        <Footer />
    </div>
</template>
