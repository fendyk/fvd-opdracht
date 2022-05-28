<script setup>
import { Head, Link } from '@inertiajs/inertia-vue3';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    laravelVersion: String,
    phpVersion: String,
})
</script>

<template>
    <Head title="Welcome" />

    <div class="relative flex items-top justify-center min-h-screen bg-gray-100 dark:bg-slate-900 sm:items-center sm:pt-0">
        <div v-if="canLogin" class="hidden fixed top-0 right-0 px-6 py-4 sm:block">
            <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="text-sm text-gray-700 underline">
                Dashboard
            </Link>

            <template v-else>
                <Link :href="route('login')" class="text-slate-200 font-bold">
                    Log in
                </Link>

                <Link v-if="canRegister" :href="route('register')" class="ml-4 text-slate-200 font-bold">
                    Register
                </Link>
            </template>
        </div>

        <div class="max-w-6xl mx-auto sm:px-6 lg:px-8">

            <div class="flex flex-col">
                
                <h1 class="text-slate-100 text-5xl"><b>FVD</b> Opdracht - Raul Fernandez van Dijk</h1>
                <p class="text-slate-400">Beheer gemakkelijk het digitale agenda van de Tweede Kamer.</p>

                <div class="text-sm text-slate-500 mt-4">
                    Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
                </div>
            </div>
        </div>
    </div>
</template>