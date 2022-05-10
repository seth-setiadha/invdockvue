<template>
    <Head title="Organizations" />

    <BreezeAuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">
                Organizations
            </h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="p-6 bg-white border-b border-gray-200">
                        

                        <table class="min-w-full border devide-y devide-gray-200">
                            <thead>
                                <tr>
                                    <th class="px-6 py-3 bg-gray-50">
                                        <span class="text-xs font-medium tracking-wide leading-4 text-left text-gray-500 uppercase">
                                            Organization Name
                                        </span>
                                    </th>
                                    <th class="px-6 py-3 bg-gray-50">
                                        <span class="text-xs font-medium tracking-wide leading-4 text-left text-gray-500 uppercase">
                                            Action
                                        </span>
                                    </th>
                                </tr>
                            </thead>
                            <tbody class="bg-white divide-y divide-gray-200 divide-solid">
                                
                                    <tr class="bg-white" v-for="organization in organizations.data" :key="organization.id">
                                        <td class="px-6 py-4 text-sm leading-5 text-gray-900 whitespace-no-wrap">
                                            {{ organization.name }}
                                        </td>
                                        <td></td>
                                    </tr>
                                
                            </tbody>
                        </table>


                    </div>
                </div>
            </div>
        </div>
    </BreezeAuthenticatedLayout>
</template>

<script>
import BreezeAuthenticatedLayout from '@/Layouts/Authenticated.vue';
import { Head } from '@inertiajs/inertia-vue3';

export default {
    components: {
        BreezeAuthenticatedLayout,
        Head
    },
    props: {
        organizations: Object,
    }
}
</script>