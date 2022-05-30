<script setup>
import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue';
import { Head } from '@inertiajs/inertia-vue3';
</script>

<template>
    <Head title="Calendar - Create" />

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Calendar / Create
            </h2>
        </template>

        <div class="mx-auto max-w-7xl p-8">
            <div class="bg-white p-8 rounded-3xl shadow-2xl shadow-slate-200">
                <div class="flex flex-row justify-between items-center">
                    <div>
                        <h2 class="text-2xl font-bold">Voeg makkelijk nieuwe items toe</h2>
                    </div>
                    <v-calendar :attributes='attrs'></v-calendar>
                    <div class="flex flex-col space-y-4">
                        <div class="flex flex-col">
                            <label class="text-gray-400">Titel</label>
                            <input type="text" placeholder="Titel invoeren.." class="rounded-3xl border-0 bg-gray-100" />
                        </div>
                        <div class="flex flex-col">
                            <label class="text-gray-400">Tag</label>
                            <input type="text" placeholder="Voer een tag in.." class="rounded-3xl border-0 bg-gray-100" />
                        </div>
                        <div class="flex flex-col">
                            <label class="text-gray-400">Tijd - van / tot</label>
                            <div class="flex flex-row">
                                <input type="time" class="rounded-3xl border-0 bg-gray-100" />
                                <input type="time" class="rounded-3xl border-0 bg-gray-100" />
                            </div>
                        </div>
                        <div class="flex flex-col">
                            <label class="text-gray-400">Selecteer gebruikers</label>
                            <select class="rounded-3xl border-0 bg-gray-100">
                                <option></option>
                            </select>
                        </div>
                        <div class="flex flex-col">
                            <input type="submit" value="Opslaan" class="rounded-3xl border-0 bg-blue-500 text-white py-2 font-bold" />
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="mx-auto max-w-7xl p-8">
            <div class="bg-white p-8 rounded-3xl shadow-2xl shadow-slate-200">

                <div>
                    <h2 class="text-2xl font-bold">5 mei 2022</h2>
                    <p class="text-purple-500">Opkomende eventen</p>
                </div>

                <div class="grid space-y-4 mt-4">
                    <div class="border-b-2 py-4 border-gray-100 grid grid-flow-col items-center justify-between">
                        <div>
                            <h3 class="text-gray-800 text-xl font-bold">Tweede kamer debat in de plenaire zaal</h3>
                            <span class="bg-blue-600 text-white px-2 py-1 rounded-3xl text-xs font-bold inline-block">Plenair debat</span>
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