<script setup>
import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue';
import { Head, Link } from '@inertiajs/inertia-vue3';
</script>

<template>
    <Head title="Dashboard" />

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Dashboard
            </h2>
        </template>

        <div class="mx-auto max-w-7xl p-8">
            <div class="bg-white p-8 shadow-2xl shadow-gray-200 rounded-3xl">
                <div class="mb-4 flex flex-row justify-between bg-white">
                    <h2 class="text-3xl font-bold">Agenda</h2>
                    <Link :href="route('calendar/Create')" class="bg-blue-600 font-bold text-white rounded-3xl px-2 py-1">
                        Nieuw item
                    </Link>
                </div>
                <v-calendar is-expanded :attributes='attrs'></v-calendar>
            </div>
        </div>

        <div class="mx-auto max-w-7xl p-8">
            <div class="bg-white p-8 rounded-3xl shadow-2xl shadow-gray-200 grid space-y-4">

                <div>
                    <h2 class="text-2xl font-bold text-gray-900">31 Mei 2022</h2>
                    <p class="text-purple-500">Opkomende eventen</p>
                </div>

                <div class="grid space-y-4">
                    <div class="border-b-2 py-4 border-gray-100 grid grid-flow-col items-center justify-between">
                        <div>
                            <h3 class="text-gray-800 text-xl font-bold">Tweede kamer debat in de plenaire zaal</h3>
                            <span class="bg-blue-600 text-white px-2 py-1 rounded-3xl text-xs font-bold inline-block">Plenair debat</span>
                        </div>
                        <div>
                            <p class="text-gray-600 mt-2">14:00 tot 15:30</p>
                        </div>
                        <div class="flex flex-col">
                            <h4 class="font-bold text-right">Raul</h4>
                            <span class="text-sm text-red-500 text-right">Administrator</span>
                        </div>
                    </div>
                    <div class="border-b-2 py-4 border-gray-100 grid grid-flow-col items-center justify-between">
                        <div>
                            <h3 class="text-gray-800 text-xl font-bold">Tweede kamer debat in de plenaire zaal</h3>
                            <span class="bg-blue-600 text-white px-2 py-1 rounded-3xl text-xs font-bold inline-block">Plenair debat</span>
                        </div>
                        <div>
                            <p class="text-gray-600 mt-2">14:00 tot 15:30</p>
                        </div>
                        <div class="flex flex-col">
                            <h4 class="font-bold text-right">Raul</h4>
                            <span class="text-sm text-red-500 text-right">Administrator</span>
                        </div>
                    </div>
                </div>

            </div>
        </div>

    </BreezeAuthenticatedLayout>
</template>

<script>
export default {
  data() {
    return {
      attrs: [
        {
          key: 'today',
          highlight: 'red',
          dates: new Date(),
        },
      ],
    };
  },
};
</script>