<script setup>
import { Head, Link } from '@inertiajs/vue3';
import DarkModeToggle from '@/Components/DarkModeToggle.vue';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
});

const businessTypes = [
  { name: 'Barberías & Salones', icon: 'ScissorsIcon', description: 'Gestiona cortes, tintes y servicios de estética con facilidad.' },
  { name: 'Clínicas Médicas', icon: 'HeartIcon', description: 'Citas médicas, historiales básicos y recordatorios para pacientes.' },
  { name: 'Gimnasios & Yoga', icon: 'UserGroupIcon', description: 'Reservas de clases grupales y entrenamientos personales.' },
  { name: 'Restaurantes', icon: 'UtensilsIcon', description: 'Control de mesas, horarios de comida y eventos especiales.' },
  { name: 'Consultorías', icon: 'BriefcaseIcon', description: 'Asesorías legales, contables o técnicas por videollamada o presencial.' },
  { name: 'Talleres Mecánicos', icon: 'WrenchIcon', description: 'Turnos para mantenimiento y reparaciones de vehículos.' },
];

const features = [
  { title: 'Calendario Inteligente', description: 'Visualiza tus citas por día, semana o mes con una interfaz intuitiva y rápida.', icon: 'CalendarIcon' },
  { title: 'Recordatorios WhatsApp', description: 'Reduce las ausencias enviando recordatorios automáticos por WhatsApp y Email.', icon: 'ChatBubbleLeftRightIcon' },
  { title: 'Gestión de Clientes', description: 'Base de datos centralizada con historial de servicios, preferencias y notas.', icon: 'UsersIcon' },
  { title: 'Panel de Estadísticas', description: 'Analiza tus ingresos, servicios más pedidos y fidelidad de clientes en tiempo real.', icon: 'ChartBarIcon' },
  { title: 'Multi-sucursal & Equipo', description: 'Gestiona varios locales y asigna citas a diferentes miembros de tu equipo.', icon: 'BuildingOfficeIcon' },
  { title: 'Pagos en Línea', description: 'Acepta pagos anticipados o señas para asegurar tus reservas desde la plataforma.', icon: 'CreditCardIcon' },
];

const pricingPlans = [
  {
    name: 'Básico',
    price: '0',
    description: 'Ideal para profesionales independientes que están comenzando.',
    features: ['Hasta 50 reservas/mes', '1 Usuario', 'Calendario básico', 'Soporte por email'],
    cta: 'Empezar Gratis',
    mostPopular: false,
  },
  {
    name: 'Profesional',
    price: '29',
    description: 'Perfecto para negocios en crecimiento con equipo pequeño.',
    features: ['Reservas ilimitadas', 'Hasta 5 usuarios', 'Recordatorios WhatsApp', 'Estadísticas avanzadas'],
    cta: 'Probar 14 días gratis',
    mostPopular: true,
  },
  {
    name: 'Enterprise',
    price: '89',
    description: 'Para empresas con múltiples sucursales y grandes equipos.',
    features: ['Multi-sucursal', 'Usuarios ilimitados', 'API personalizada', 'Soporte prioritario 24/7'],
    cta: 'Contactar Ventas',
    mostPopular: false,
  },
];
</script>

<template>
    <Head title="Sistema de Reservas SaaS - Gestiona tu negocio" />

    <div class="min-h-screen bg-white font-sans text-gray-900 selection:bg-indigo-500 selection:text-white dark:bg-gray-950 dark:text-gray-100 transition-colors duration-300">
        <!-- Navigation -->
        <nav class="sticky top-0 z-50 border-b border-gray-100 bg-white/80 backdrop-blur-md dark:border-gray-800 dark:bg-gray-950/80">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="flex h-20 items-center justify-between">
                    <div class="flex items-center">
                        <Link href="/" class="flex items-center gap-2 group">
                            <div class="flex h-11 w-11 items-center justify-center rounded-xl bg-indigo-600 text-white shadow-lg shadow-indigo-200 dark:shadow-none transition-transform group-hover:scale-110">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="h-6 w-6">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" />
                                </svg>
                            </div>
                            <span class="text-2xl font-bold tracking-tight text-gray-900 dark:text-white">Reserva<span class="text-indigo-600 dark:text-indigo-400">Pro</span></span>
                        </Link>
                    </div>
                    <div class="hidden md:block">
                        <div class="ml-10 flex items-baseline space-x-8">
                            <a href="#soluciones" class="text-sm font-medium text-gray-600 hover:text-indigo-600 dark:text-gray-400 dark:hover:text-indigo-400 transition-colors">Soluciones</a>
                            <a href="#caracteristicas" class="text-sm font-medium text-gray-600 hover:text-indigo-600 dark:text-gray-400 dark:hover:text-indigo-400 transition-colors">Características</a>
                            <a href="#precios" class="text-sm font-medium text-gray-600 hover:text-indigo-600 dark:text-gray-400 dark:hover:text-indigo-400 transition-colors">Precios</a>
                        </div>
                    </div>
                    <div class="flex items-center gap-4">
                        <DarkModeToggle />
                        <template v-if="canLogin">
                            <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="text-sm font-semibold text-gray-900 hover:text-indigo-600 dark:text-gray-100 dark:hover:text-indigo-400">Dashboard</Link>
                            <template v-else>
                                <Link :href="route('login')" class="hidden sm:block text-sm font-semibold text-gray-900 hover:text-indigo-600 dark:text-gray-100 dark:hover:text-indigo-400">Iniciar Sesión</Link>
                                <Link v-if="canRegister" :href="route('register')" class="rounded-xl bg-indigo-600 px-5 py-2.5 text-sm font-semibold text-white shadow-md hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600 transition-all active:scale-95">Registrarse</Link>
                            </template>
                        </template>
                    </div>
                </div>
            </div>
        </nav>

        <!-- Hero Section -->
        <header class="relative overflow-hidden pt-16 pb-32 sm:pt-24 sm:pb-40">
            <!-- Background decoration -->
            <div class="absolute top-0 left-1/2 -translate-x-1/2 blur-3xl opacity-20 dark:opacity-10 pointer-events-none -z-10">
                <div class="aspect-[1100/600] w-[70rem] bg-gradient-to-tr from-indigo-500 to-emerald-400"></div>
            </div>
            
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="lg:grid lg:grid-cols-12 lg:gap-12 items-center">
                    <div class="sm:text-center md:mx-auto md:max-w-2xl lg:col-span-6 lg:text-left">
                        <span class="inline-flex items-center rounded-full bg-indigo-50 px-3 py-1 text-sm font-medium text-indigo-700 ring-1 ring-inset ring-indigo-700/10 mb-6 dark:bg-indigo-900/30 dark:text-indigo-300 dark:ring-indigo-500/20">
                            ✨ Nueva Integración con WhatsApp
                        </span>
                        <h1 class="text-5xl font-extrabold tracking-tight text-gray-900 sm:text-7xl dark:text-white">
                            Gestiona tus citas <span class="text-transparent bg-clip-text bg-gradient-to-r from-indigo-600 to-emerald-500 dark:from-indigo-400 dark:to-emerald-400">sin complicaciones</span>
                        </h1>
                        <p class="mt-8 text-lg leading-8 text-gray-600 dark:text-gray-400">
                            La plataforma SaaS definitiva para negocios que buscan automatizar su agenda, reducir ausencias y ofrecer una experiencia premium a sus clientes.
                        </p>
                        <div class="mt-10 flex flex-col sm:flex-row sm:justify-center lg:justify-start gap-4">
                            <Link :href="route('register')" class="rounded-xl bg-indigo-600 px-8 py-4 text-lg font-semibold text-white shadow-xl shadow-indigo-200 dark:shadow-none hover:bg-indigo-500 transition-all text-center active:scale-95">
                                Empezar ahora gratis
                            </Link>
                            <a href="#soluciones" class="rounded-xl bg-white px-8 py-4 text-lg font-semibold text-gray-900 ring-1 ring-gray-200 hover:bg-gray-50 transition-all text-center dark:bg-gray-900 dark:text-white dark:ring-gray-800 dark:hover:bg-gray-800">
                                Explorar soluciones
                            </a>
                        </div>
                        <div class="mt-10 flex items-center gap-4 text-sm text-gray-500 dark:text-gray-400 sm:justify-center lg:justify-start">
                            <div class="flex -space-x-2">
                                <img class="h-9 w-9 rounded-full ring-2 ring-white dark:ring-gray-950" src="https://images.unsplash.com/photo-1491528323818-fdd1faba62cc?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
                                <img class="h-9 w-9 rounded-full ring-2 ring-white dark:ring-gray-950" src="https://images.unsplash.com/photo-1550525811-e5869dd03032?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
                                <img class="h-9 w-9 rounded-full ring-2 ring-white dark:ring-gray-950" src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-1.2.1&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80" alt="">
                            </div>
                            <p><span class="font-bold text-gray-900 dark:text-white">+1,200</span> negocios optimizados este mes</p>
                        </div>
                    </div>
                    <div class="relative mt-16 sm:mx-auto sm:max-w-lg lg:col-span-6 lg:mx-0 lg:mt-0 lg:flex lg:items-center">
                        <div class="relative mx-auto w-full rounded-2xl shadow-2xl overflow-hidden ring-1 ring-gray-900/10 dark:ring-white/10">
                            <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?ixlib=rb-4.0.3&auto=format&fit=crop&w=1000&q=80" alt="Dashboard Preview" class="w-full">
                            <div class="absolute inset-0 bg-gradient-to-tr from-indigo-600/20 to-transparent mix-blend-multiply"></div>
                        </div>
                        <!-- Floating badge -->
                        <div class="absolute -bottom-6 -left-6 bg-white dark:bg-gray-800 p-4 rounded-xl shadow-xl ring-1 ring-gray-900/10 dark:ring-white/10 hidden sm:block">
                            <div class="flex items-center gap-3">
                                <div class="h-10 w-10 rounded-full bg-emerald-100 dark:bg-emerald-900/50 flex items-center justify-center text-emerald-600 dark:text-emerald-400">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                                    </svg>
                                </div>
                                <div>
                                    <p class="text-xs text-gray-500 dark:text-gray-400 font-medium">Citas confirmadas hoy</p>
                                    <p class="text-lg font-bold text-gray-900 dark:text-white">482 nuevas</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <!-- Business Types Section -->
        <section id="soluciones" class="bg-gray-50 dark:bg-gray-900/50 py-24 sm:py-32 transition-colors">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="max-w-2xl mx-auto text-center">
                    <h2 class="text-indigo-600 dark:text-indigo-400 font-semibold tracking-wide uppercase text-sm">Versatilidad total</h2>
                    <p class="mt-3 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl dark:text-white">Diseñado para tu industria</p>
                    <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">Nuestra interfaz flexible se adapta a las necesidades específicas de tu sector.</p>
                </div>
                <div class="mt-16 grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
                    <div v-for="type in businessTypes" :key="type.name" class="relative group bg-white dark:bg-gray-800 p-8 rounded-2xl shadow-sm hover:shadow-xl hover:-translate-y-1 transition-all border border-gray-100 dark:border-gray-700">
                        <div class="flex h-12 w-12 items-center justify-center rounded-xl bg-indigo-50 text-indigo-600 group-hover:bg-indigo-600 group-hover:text-white dark:bg-indigo-900/20 dark:text-indigo-400 dark:group-hover:bg-indigo-500 transition-colors mb-6">
                            <!-- Icons based on type -->
                            <svg v-if="type.icon === 'ScissorsIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M7.848 8.25V5.25a3.375 3.375 0 0 0-3.375-3.375 3.375 3.375 0 0 0-3.375 3.375V5.25c0 .616.33 1.158.825 1.463a3.376 3.376 0 0 0 1.725 2.537v11.475a.75.75 0 0 0 1.5 0V9.25c.66-.234 1.25-.63 1.725-1.15.495-.305.825-.847.825-1.463ZM16.152 8.25V5.25a3.375 3.375 0 0 1 3.375-3.375 3.375 3.375 0 0 1 3.375 3.375V5.25c0 .616-.33 1.158-.825 1.463a3.376 3.376 0 0 1-1.725 2.537v11.475a.75.75 0 0 1-1.5 0V9.25c-.66-.234-1.25-.63-1.725-1.15a1.875 1.875 0 0 1-.825-1.463ZM12 8.25a.75.75 0 0 1 .75.75v10.5a.75.75 0 0 1-1.5 0V9a.75.75 0 0 1 .75-.75Z" /></svg>
                            <svg v-else-if="type.icon === 'HeartIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12Z" /></svg>
                            <svg v-else-if="type.icon === 'UserGroupIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M18 18.72a9.094 9.094 0 0 0 3.741-.479 3 3 0 0 0-4.682-2.72m.94 3.198.001.031c0 .225-.012.447-.037.666A11.944 11.944 0 0 1 12 21c-2.17 0-4.207-.576-5.963-1.584A6.062 6.062 0 0 1 6 18.719m12 0a5.971 5.971 0 0 0-.941-3.197m0 0A5.995 5.995 0 0 0 12 12.75a5.995 5.995 0 0 0-5.058 2.772m0 0a5.97 5.97 0 0 0-.942 3.197M12 10.5a3 3 0 1 1 0-6 3 3 0 0 1 0 6Zm-7 3.25V13.5a3 3 0 0 1 6 0v.25m10-1.25V13.5a3 3 0 0 0-6 0v.25" /></svg>
                            <svg v-else-if="type.icon === 'UtensilsIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M13.5 21v-7.5a.75.75 0 0 1 .75-.75h3a.75.75 0 0 1 .75.75V21m-10.5 0v-7.5a.75.75 0 0 1 .75-.75h3a.75.75 0 0 1 .75.75V21m-4.5-16.5H21" /></svg>
                            <svg v-else-if="type.icon === 'BriefcaseIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M20.25 14.15v4.25c0 .414-.336.75-.75.75H4.5a.75.75 0 0 1-.75-.75v-4.25m16.5 0a3 3 0 0 0-3-3H7.125a3 3 0 0 0-3 3m16.5 0V9.375c0-.621-.504-1.125-1.125-1.125H3.375c-.621 0-1.125.504-1.125 1.125v4.775" /></svg>
                            <svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M11.42 15.17L17.25 21A2.652 2.652 0 0021 17.25l-5.83-5.83m0 0a8.959 8.959 0 01-5.83 1.352 8.959 8.959 0 01-4.588-4.588 8.959 8.959 0 011.352-5.83m0 0A2.652 2.652 0 0117.25 3a2.652 2.652 0 013 3.5l-5.83 5.83" /></svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-2">{{ type.name }}</h3>
                        <p class="text-gray-600 dark:text-gray-400 leading-relaxed">{{ type.description }}</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Features Section -->
        <section id="caracteristicas" class="py-24 sm:py-32">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="max-w-2xl mx-auto lg:text-center">
                    <h2 class="text-emerald-600 dark:text-emerald-400 font-semibold tracking-wide uppercase text-sm">Control total</h2>
                    <p class="mt-3 text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl dark:text-white">Potencia tu eficiencia diaria</p>
                    <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">Herramientas diseñadas por expertos en gestión operativa para que tú te enfoques en lo que importa.</p>
                </div>

                <div class="mt-20">
                    <div class="grid grid-cols-1 gap-y-12 sm:grid-cols-2 sm:gap-x-12 lg:grid-cols-3">
                        <div v-for="feature in features" :key="feature.title" class="group flex flex-col p-6 rounded-2xl transition-colors hover:bg-gray-50 dark:hover:bg-gray-900">
                            <div class="flex h-12 w-12 items-center justify-center rounded-xl bg-indigo-600 text-white shadow-lg shadow-indigo-200 dark:shadow-none mb-6">
                                <svg v-if="feature.icon === 'CalendarIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" /></svg>
                                <svg v-else-if="feature.icon === 'ChatBubbleLeftRightIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M7.5 8.25h9m-9 3H12m-9.75 1.51c0 1.6 1.123 2.994 2.707 3.227 1.129.166 2.27.293 3.423.379.35.026.67.21.865.501L12 21l2.755-4.133a1.14 1.14 0 0 1 .865-.501 48.172 48.172 0 0 0 3.423-.379c1.584-.233 2.707-1.626 2.707-3.228V6.741c0-1.602-1.123-2.995-2.707-3.228A48.394 48.394 0 0 0 12 3c-2.392 0-4.744.175-7.043.513C3.373 3.746 2.25 5.14 2.25 6.741v6.028Z" /></svg>
                                <svg v-else-if="feature.icon === 'UsersIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M15 19.128a9.38 9.38 0 0 0 2.625.372 9.337 9.337 0 0 0 4.121-.952 4.125 4.125 0 0 0-7.533-2.493M15 19.128v-.003c0-1.113-.285-2.16-.786-3.07M15 19.128v.106A12.318 12.318 0 0 1 8.624 21c-2.331 0-4.512-.645-6.374-1.766l-.001-.109a6.375 6.375 0 0 1 11.964-3.07M12 6.375a3.375 3.375 0 1 1-6.75 0 3.375 3.375 0 0 1 6.75 0Zm8.25 2.25a2.625 2.625 0 1 1-5.25 0 2.625 2.625 0 0 1 5.25 0Z" /></svg>
                                <svg v-else-if="feature.icon === 'ChartBarIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M3 13.125C3 12.504 3.504 12 4.125 12h2.25c.621 0 1.125.504 1.125 1.125v6.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 0 1-1.125-1.125v-6.75ZM9.75 8.625c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v11.25c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 0 1-1.125-1.125V8.625ZM16.5 4.125c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125v15.75c0 .621-.504 1.125-1.125 1.125h-2.25a1.125 1.125 0 0 1-1.125-1.125V4.125Z" /></svg>
                                <svg v-else-if="feature.icon === 'BuildingOfficeIcon'" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 21h16.5M4.5 3h15M5.25 3v18m13.5-18v18M9 6.75h1.5m-1.5 3h1.5m-1.5 3h1.5m3-6H15m-1.5 3H15m-1.5 3H15M9 21v-3.375c0-.621.504-1.125 1.125-1.125h3.75c.621 0 1.125.504 1.125 1.125V21" /></svg>
                                <svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M2.25 8.25h19.5M2.25 9h19.5m-16.5 5.25h6m-6 2.25h3m-3.75-10.5h16.5a1.5 1.5 0 0 1 1.5 1.5v10.5a1.5 1.5 0 0 1-1.5 1.5H3.75a1.5 1.5 0 0 1-1.5-1.5V5.25a1.5 1.5 0 0 1 1.5-1.5Z" /></svg>
                            </div>
                            <h3 class="text-xl font-bold text-gray-900 dark:text-white mb-2">{{ feature.title }}</h3>
                            <p class="text-gray-600 dark:text-gray-400 leading-relaxed">{{ feature.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Pricing Section -->
        <section id="precios" class="bg-gray-50 dark:bg-gray-900/50 py-24 sm:py-32 transition-colors">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl dark:text-white">Planes que crecen contigo</h2>
                    <p class="mt-4 text-lg text-gray-600 dark:text-gray-400">Sin comisiones ocultas. Cancela cuando quieras.</p>
                </div>

                <div class="grid grid-cols-1 gap-8 lg:grid-cols-3">
                    <div v-for="plan in pricingPlans" :key="plan.name"
                         :class="[plan.mostPopular ? 'ring-2 ring-indigo-600 shadow-2xl dark:ring-indigo-500 scale-105 z-10' : 'ring-1 ring-gray-200 dark:ring-gray-800 shadow-sm',
                                 'relative flex flex-col rounded-3xl bg-white dark:bg-gray-800 p-8 transition-all']">
                        <div v-if="plan.mostPopular" class="absolute -top-4 left-1/2 -translate-x-1/2 rounded-full bg-indigo-600 px-4 py-1 text-sm font-semibold text-white">
                            Sugerido
                        </div>
                        <h3 class="text-lg font-semibold leading-8 text-gray-900 dark:text-white">{{ plan.name }}</h3>
                        <p class="mt-4 text-sm leading-6 text-gray-600 dark:text-gray-400">{{ plan.description }}</p>
                        <p class="mt-6 flex items-baseline gap-x-1">
                            <span class="text-5xl font-extrabold tracking-tight text-gray-900 dark:text-white">${{ plan.price }}</span>
                            <span v-if="plan.price !== '0'" class="text-sm font-semibold leading-6 text-gray-600 dark:text-gray-400">/mes</span>
                        </p>
                        <ul role="list" class="mt-8 space-y-3 text-sm leading-6 text-gray-600 dark:text-gray-400">
                            <li v-for="feature in plan.features" :key="feature" class="flex gap-x-3">
                                <svg class="h-6 w-5 flex-none text-emerald-600 dark:text-emerald-400" viewBox="0 0 20 20" fill="currentColor">
                                    <path fill-rule="evenodd" d="M16.704 4.153a.75.75 0 01.143 1.052l-8 10.5a.75.75 0 01-1.127.075l-4.5-4.5a.75.75 0 011.06-1.06l3.894 3.893 7.48-9.817a.75.75 0 011.05-.143z" clip-rule="evenodd" />
                                </svg>
                                {{ feature }}
                            </li>
                        </ul>
                        <div class="mt-auto pt-10">
                            <Link :href="route('register')"
                                  :class="[plan.mostPopular ? 'bg-indigo-600 text-white hover:bg-indigo-500 shadow-lg shadow-indigo-200 dark:shadow-none' : 'bg-gray-50 text-gray-900 ring-1 ring-inset ring-gray-200 hover:bg-gray-100 dark:bg-gray-700 dark:text-white dark:ring-gray-600 dark:hover:bg-gray-600',
                                          'block rounded-xl px-3 py-3 text-center text-sm font-semibold leading-6 transition-all active:scale-95']">
                                {{ plan.cta }}
                            </Link>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Final CTA -->
        <section class="py-24 sm:py-32 overflow-hidden">
            <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
                <div class="relative isolate overflow-hidden bg-indigo-600 px-6 py-24 shadow-2xl rounded-[3rem] sm:px-24 xl:py-32 text-center">
                    <h2 class="mx-auto max-w-2xl text-3xl font-bold tracking-tight text-white sm:text-5xl">Comienza a recibir reservas hoy mismo</h2>
                    <p class="mx-auto mt-6 max-w-xl text-lg leading-8 text-indigo-100">Únete a la nueva era de la gestión de servicios. Configuración en menos de 10 minutos.</p>
                    <div class="mt-10 flex items-center justify-center gap-x-6">
                        <Link :href="route('register')" class="rounded-xl bg-white px-8 py-4 text-lg font-semibold text-indigo-600 shadow-sm hover:bg-indigo-50 transition-all active:scale-95">
                            Crear cuenta gratuita
                        </Link>
                        <a href="#" class="text-lg font-semibold leading-6 text-white hover:underline">Solicitar Demo <span aria-hidden="true">→</span></a>
                    </div>
                    <!-- Decorative circles -->
                    <svg viewBox="0 0 1024 1024" class="absolute left-1/2 top-1/2 -z-10 h-[64rem] w-[64rem] -translate-x-1/2 [mask-image:radial-gradient(closest-side,white,transparent)]" aria-hidden="true">
                        <circle cx="512" cy="512" r="512" fill="url(#gradient)" fill-opacity="0.3" />
                        <defs>
                            <radialGradient id="gradient">
                                <stop stop-color="white" />
                                <stop offset="1" stop-color="#4F46E5" />
                            </radialGradient>
                        </defs>
                    </svg>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="bg-white dark:bg-gray-950 border-t border-gray-100 dark:border-gray-800 transition-colors">
            <div class="mx-auto max-w-7xl px-4 py-16 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 md:grid-cols-4 gap-12 mb-12">
                    <div class="col-span-1 md:col-span-2">
                        <div class="flex items-center gap-2 mb-6">
                            <div class="flex h-9 w-9 items-center justify-center rounded-lg bg-indigo-600 text-white">
                                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2.5" stroke="currentColor" class="h-5 w-5">
                                    <path stroke-linecap="round" stroke-linejoin="round" d="M6.75 3v2.25M17.25 3v2.25M3 18.75V7.5a2.25 2.25 0 0 1 2.25-2.25h13.5A2.25 2.25 0 0 1 21 7.5v11.25m-18 0A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75m-18 0v-7.5A2.25 2.25 0 0 1 5.25 9h13.5A2.25 2.25 0 0 1 21 11.25v7.5m-9-6h.008v.008H12v-.008ZM12 15h.008v.008H12V15Zm0 2.25h.008v.008H12v-.008ZM9.75 15h.008v.008H9.75V15Zm0 2.25h.008v.008H9.75v-.008ZM7.5 15h.008v.008H7.5V15Zm0 2.25h.008v.008H7.5v-.008Zm6.75-4.5h.008v.008h-.008v-.008Zm0 2.25h.008v.008h-.008V15Zm0 2.25h.008v.008h-.008v-.008Zm2.25-4.5h.008v.008H16.5v-.008Zm0 2.25h.008v.008H16.5V15Z" />
                                </svg>
                            </div>
                            <span class="text-xl font-bold tracking-tight text-gray-900 dark:text-white">ReservaPro</span>
                        </div>
                        <p class="text-gray-600 dark:text-gray-400 max-w-sm">Simplificando la gestión de servicios para negocios modernos en todo el mundo.</p>
                    </div>
                    <div>
                        <h4 class="font-bold text-gray-900 dark:text-white mb-6">Producto</h4>
                        <ul class="space-y-4 text-sm text-gray-600 dark:text-gray-400">
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">Características</a></li>
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">Precios</a></li>
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">API</a></li>
                        </ul>
                    </div>
                    <div>
                        <h4 class="font-bold text-gray-900 dark:text-white mb-6">Empresa</h4>
                        <ul class="space-y-4 text-sm text-gray-600 dark:text-gray-400">
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">Sobre nosotros</a></li>
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">Contacto</a></li>
                            <li><a href="#" class="hover:text-indigo-600 dark:hover:text-indigo-400">Blog</a></li>
                        </ul>
                    </div>
                </div>
                <div class="pt-8 border-t border-gray-100 dark:border-gray-800 flex flex-col md:flex-row justify-between items-center gap-4">
                    <p class="text-sm text-gray-500 dark:text-gray-500">© 2026 ReservaPro. Hecho con ❤️ para emprendedores.</p>
                    <div class="flex space-x-6 text-sm">
                        <a href="#" class="text-gray-500 hover:text-gray-900 dark:hover:text-white">Privacidad</a>
                        <a href="#" class="text-gray-500 hover:text-gray-900 dark:hover:text-white">Términos</a>
                    </div>
                </div>
            </div>
        </footer>
    </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}
</style>
