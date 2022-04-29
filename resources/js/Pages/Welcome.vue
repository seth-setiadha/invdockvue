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
    <div>
        <Head title="Welcome" />

        <div class="relative flex items-top justify-center min-h-screen bg-gray-100 dark:bg-gray-900 sm:items-center sm:pt-0">
            <div v-if="canLogin" class="hidden fixed top-0 right-0 px-6 py-4 sm:block">
                <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="text-sm text-gray-700 underline">
                    Dashboard
                </Link>

                <template v-else>
                    <Link :href="route('login')" class="text-sm text-gray-700 underline">
                        Log in
                    </Link>

                    <Link v-if="canRegister" :href="route('register')" class="ml-4 text-sm text-gray-700 underline">
                        Register
                    </Link>
                </template>
            </div>

            <div class="max-w-6xl mx-auto sm:px-6 lg:px-8">
                <div class="flex justify-center pt-8 sm:justify-start sm:pt-0"><svg version="1.0" xmlns="http://www.w3.org/2000/svg" width="240pt" height="105pt" viewBox="0 0 300.000000 131.000000" preserveAspectRatio="xMidYMid meet"><g transform="translate(0.000000,131.000000) scale(0.100000,-0.100000)" fill="#000000" stroke="none"><path d="M724 1226 c-63 -20 -129 -70 -187 -144 -73 -92 -177 -261 -177 -287 0 -3 5 -5 10 -5 6 0 10 6 10 14 0 8 4 16 8 18 4 2 26 32 47 68 145 240 254 329 389 318 70 -6 111 -42 132 -116 13 -44 14 -65 6 -108 -19 -93 -85 -188 -163 -233 -55 -32 -174 -91 -184 -91 -17 0 -55 -44 -55 -62 0 -22 39 -113 78 -183 88 -158 202 -261 323 -294 52 -14 94 -9 152 20 36 19 97 90 97 114 0 7 7 18 15 25 24 20 65 -12 65 -51 0 -42 -27 -95 -60 -119 -47 -34 -144 -53 -227 -45 -40 4 -75 11 -79 16 -3 5 -11 9 -19 9 -8 0 -42 17 -77 37 -139 81 -304 290 -363 459 -25 72 -10 99 76 129 166 58 267 136 315 243 25 55 31 129 14 162 -17 31 -73 59 -109 55 -66 -8 -120 -56 -220 -195 -34 -47 -66 -90 -71 -97 -6 -7 -10 -16 -10 -22 0 -5 -4 -11 -8 -13 -10 -4 -121 -203 -158 -283 -16 -33 -40 -94 -55 -135 -28 -80 -36 -87 -94 -76 -40 8 -43 19 -33 101 10 76 64 299 84 345 8 19 41 96 73 170 56 131 59 135 97 148 27 9 45 10 61 3 28 -13 24 -29 -52 -183 -31 -65 -55 -123 -52 -130 4 -8 6 -6 6 5 1 9 5 17 10 17 16 0 142 260 139 288 -3 26 -5 27 -73 30 -38 1 -76 -2 -83 -6 -16 -11 -125 -261 -162 -372 -45 -136 -73 -269 -74 -350 l-1 -75 40 -14 c26 -9 55 -11 77 -7 35 6 37 9 58 79 40 134 129 305 257 496 143 213 218 275 298 245 27 -11 46 -59 39 -101 -20 -126 -114 -223 -279 -287 -38 -15 -82 -32 -97 -37 -34 -14 -61 -69 -52 -106 26 -102 143 -291 242 -390 132 -131 247 -187 382 -186 128 0 207 38 249 121 35 69 25 119 -29 147 -47 24 -59 19 -83 -38 -58 -130 -178 -161 -312 -81 -101 60 -192 180 -266 348 -28 65 -31 80 -19 84 8 3 67 31 130 63 143 72 206 129 244 224 43 108 30 233 -30 287 -51 45 -132 58 -210 34z"></path> <path d="M2095 1211 c-49 -22 -73 -48 -81 -88 -7 -35 15 -63 50 -63 30 0 41 14 56 70 13 49 35 80 57 80 7 0 13 5 13 10 0 16 -51 11 -95 -9z m11 -56 c-9 -9 -16 -25 -16 -35 0 -20 -29 -35 -42 -22 -13 13 7 57 33 76 29 20 49 5 25 -19z"></path> <path d="M2499 1210 c-19 -10 -41 -31 -47 -46 l-13 -27 25 17 c31 20 53 20 99 1 49 -20 64 -19 77 6 9 16 8 26 -5 45 -12 19 -24 24 -58 24 -23 -1 -58 -9 -78 -20z m111 -27 c0 -10 -7 -12 -20 -9 -11 3 -30 9 -41 12 -31 9 -6 22 31 16 18 -2 30 -10 30 -19z"></path> <path d="M2171 1184 c-17 -14 -31 -29 -31 -34 0 -7 39 -18 85 -23 24 -2 32 31 15 62 -14 28 -32 26 -69 -5z"></path> <path d="M2762 1164 c-23 -16 -30 -58 -11 -70 7 -4 29 -8 50 -9 35 -2 38 0 44 32 11 58 -33 83 -83 47z m54 -25 c9 -16 -10 -31 -30 -23 -13 5 -14 9 -5 20 14 17 25 18 35 3z"></path> <path d="M2856 1158 c13 -21 11 -72 -3 -86 -21 -22 -13 -66 13 -70 56 -8 74 83 28 137 -25 30 -53 44 -38 19z m30 -116 c-11 -10 -14 3 -8 33 l7 30 3 -28 c2 -16 1 -31 -2 -35z"></path> <path d="M2462 1138 c-31 -31 6 -106 46 -94 17 6 22 15 22 45 0 20 5 42 12 49 9 9 3 12 -28 12 -22 0 -45 -5 -52 -12z m38 -33 c0 -14 -4 -25 -10 -25 -5 0 -10 11 -10 25 0 14 5 25 10 25 6 0 10 -11 10 -25z"></path> <path d="M2250 1093 c-30 -11 -50 -37 -50 -63 0 -56 47 -66 104 -21 44 35 29 55 -16 21 -32 -24 -61 -20 -56 7 8 40 65 39 188 -5 30 -11 -12 28 -51 49 -37 18 -88 23 -119 12z"></path> <path d="M2590 1039 c-26 -11 -60 -38 -60 -49 0 -4 13 -5 30 -2 17 2 52 -5 84 -18 61 -26 86 -22 86 14 0 54 -72 82 -140 55z m100 -34 c7 -9 10 -18 7 -21 -9 -9 -88 16 -82 26 10 16 61 12 75 -5z"></path> <path d="M1396 1000 c-28 -33 -45 -114 -29 -139 5 -9 30 -27 55 -41 52 -29 88 -58 88 -73 0 -6 -24 -67 -54 -136 -64 -151 -71 -177 -56 -230 13 -49 41 -78 92 -93 41 -12 96 -1 131 26 16 12 17 17 5 38 -7 12 -13 24 -14 26 0 1 -18 -5 -39 -13 -34 -15 -39 -15 -57 2 -31 28 -13 91 66 228 44 74 53 123 31 164 -14 28 -78 84 -106 93 -6 2 -4 16 5 33 31 63 30 82 -2 115 -41 40 -81 40 -116 0z m99 -24 c14 -21 14 -28 0 -69 -13 -38 -13 -50 -3 -67 7 -11 16 -20 20 -20 5 0 26 -16 48 -36 54 -49 52 -88 -5 -189 -54 -94 -75 -147 -75 -188 1 -46 23 -70 65 -71 44 -1 45 -13 2 -21 -63 -12 -116 27 -122 90 -4 37 17 120 40 165 15 28 53 113 65 146 11 28 -20 79 -61 102 -62 34 -79 52 -79 85 0 78 70 127 105 73z"></path> <path d="M2347 1017 c-16 -11 -15 -15 12 -45 34 -36 43 -39 65 -16 24 24 20 53 -10 64 -33 13 -47 13 -67 -3z m58 -28 c12 -18 -3 -22 -20 -5 -14 14 -14 16 -1 16 8 0 18 -5 21 -11z"></path> <path d="M2523 956 c-4 -7 -28 -16 -53 -20 -50 -9 -60 -9 -140 -6 -30 1 -77 -2 -105 -7 l-50 -9 80 -39 c54 -27 90 -39 112 -37 17 2 46 -4 63 -13 26 -14 37 -14 61 -5 17 7 46 10 71 6 33 -5 53 -2 83 14 21 11 53 20 70 20 16 0 52 10 78 22 l48 23 -73 11 c-87 13 -158 7 -158 -13 0 -7 -11 -19 -25 -25 -21 -9 -28 -8 -45 7 -30 27 -25 52 10 60 18 4 36 2 44 -4 10 -8 16 -8 25 3 9 11 8 15 -5 20 -28 11 -83 6 -91 -8z m-7 -74 c11 -15 8 -18 -19 -28 -18 -6 -39 -8 -47 -4 -8 4 -38 10 -67 13 -29 3 -57 8 -62 12 -27 16 -4 22 86 23 80 1 99 -2 109 -16z"></path> <path d="M2127 903 c-17 -16 -4 -110 29 -215 38 -120 46 -215 25 -272 -7 -16 -9 -31 -6 -35 3 -3 50 -7 103 -9 122 -5 222 15 320 64 90 44 197 140 206 185 3 17 22 66 41 109 35 77 56 170 39 170 -5 0 -40 -16 -77 -35 -39 -20 -83 -35 -103 -35 -19 0 -46 -7 -60 -16 -18 -12 -37 -15 -74 -11 -26 3 -62 1 -78 -5 -23 -9 -37 -8 -68 4 -22 9 -51 14 -64 11 -17 -3 -57 12 -124 46 -111 57 -101 53 -109 44z m127 -84 c33 -17 83 -33 111 -36 27 -3 57 -9 65 -13 8 -4 26 -6 40 -4 14 3 54 5 90 5 36 1 77 7 92 15 15 8 41 14 58 14 17 0 54 7 81 16 27 9 53 14 56 10 10 -9 -29 -86 -49 -97 -10 -5 -18 -16 -18 -25 0 -46 -89 -165 -123 -164 -7 1 -2 9 11 19 35 30 26 34 -20 10 -24 -12 -54 -25 -68 -30 -20 -6 -16 -7 22 -8 26 -1 49 -5 52 -10 11 -17 -41 -50 -124 -81 -88 -32 -230 -50 -285 -36 -26 7 -27 9 -23 55 8 82 -7 170 -46 274 -48 124 -32 142 78 86z"></path> <path d="M2726 697 c-20 -25 -66 -64 -102 -87 -65 -43 -84 -67 -39 -50 75 29 146 83 171 132 26 50 10 53 -30 5z"></path> <path d="M1915 859 c-48 -15 -121 -74 -165 -134 -137 -185 -158 -376 -46 -413 36 -12 44 -11 92 13 51 25 134 103 134 126 0 13 -5 9 -85 -58 -60 -49 -91 -63 -129 -56 -43 9 -59 43 -54 118 11 170 218 420 315 380 15 -6 15 -8 3 -12 -32 -11 -137 -130 -180 -203 -36 -62 -72 -144 -77 -175 -7 -43 18 -85 49 -85 30 0 113 89 184 197 61 91 77 104 100 81 13 -12 10 -23 -21 -86 -43 -84 -41 -113 8 -159 75 -72 264 -86 492 -37 65 14 177 76 229 128 51 49 106 138 106 169 0 8 9 22 20 32 18 16 20 17 26 1 9 -24 -2 -95 -21 -133 -18 -36 -117 -131 -161 -153 -16 -8 -31 -17 -34 -20 -12 -12 -60 -31 -130 -50 -41 -11 -86 -24 -100 -28 -37 -11 -254 -6 -319 8 -89 19 -143 49 -164 93 -20 39 -37 49 -37 20 0 -58 75 -113 186 -135 101 -20 306 -15 404 11 258 67 418 216 408 378 -2 40 -7 49 -24 51 -29 4 -71 -33 -79 -71 -28 -129 -171 -245 -360 -292 -155 -39 -360 -16 -428 47 -37 35 -34 69 12 146 41 69 40 89 -4 108 -19 7 -40 14 -48 14 -7 0 -41 -42 -74 -92 -71 -108 -158 -208 -180 -208 -26 0 -11 91 27 163 70 133 171 257 211 257 25 0 35 -25 21 -55 -10 -21 -8 -26 8 -35 10 -5 30 -10 44 -10 23 0 26 4 26 35 0 19 -5 46 -12 60 -23 51 -111 84 -173 64z m156 -122 c-13 -13 -26 -3 -16 12 3 6 11 8 17 5 6 -4 6 -10 -1 -17z"></path> <path d="M1003 831 c-61 -44 -131 -129 -170 -209 -89 -178 -34 -311 138 -337 118 -18 241 67 362 250 46 70 127 217 127 231 0 1 -15 11 -34 22 l-34 20 -42 -81 c-81 -157 -206 -319 -273 -354 -17 -8 -53 -16 -80 -16 -42 -1 -53 3 -73 27 -13 15 -24 38 -24 51 0 13 -4 27 -10 30 -6 4 -10 -9 -10 -33 0 -43 25 -77 68 -93 30 -12 128 -3 137 12 8 12 35 12 35 0 0 -17 -66 -36 -126 -35 -112 3 -176 57 -176 150 0 138 140 339 255 368 50 12 48 -4 -6 -57 -69 -68 -103 -111 -133 -169 -38 -74 -29 -108 28 -108 21 0 42 13 76 48 57 56 108 129 118 166 9 37 24 43 24 9 0 -69 -96 -198 -169 -229 -21 -9 -52 -14 -73 -11 -41 5 -50 -6 -19 -23 71 -38 199 50 267 182 39 77 27 163 -28 202 -37 27 -109 21 -155 -13z m137 -64 c0 -69 -137 -247 -191 -247 -18 0 -20 4 -14 27 14 57 166 253 196 253 5 0 9 -15 9 -33z m245 -90 c-36 -69 -93 -161 -125 -201 -35 -44 -99 -106 -109 -106 -6 0 -11 -5 -11 -12 0 -9 -3 -9 -12 0 -9 9 -10 15 -2 20 33 22 63 53 100 102 76 104 90 125 129 195 46 85 58 101 63 86 2 -6 -13 -44 -33 -84z"></path> <path d="M2730 339 c-117 -59 -254 -89 -410 -88 -63 0 -134 4 -158 8 -41 8 -44 7 -54 -18 -16 -40 -22 -117 -9 -125 6 -4 48 5 93 20 147 48 293 37 541 -41 111 -35 107 -37 107 43 -1 74 -31 225 -45 227 -6 1 -35 -11 -65 -26z m61 -86 c19 -65 22 -113 8 -129 -7 -9 -22 -7 -59 7 -26 10 -59 20 -72 23 -13 2 -69 14 -125 25 -55 12 -113 21 -127 21 -54 0 -23 16 62 32 161 29 214 43 247 65 36 24 49 16 66 -44z m-497 -38 c45 -6 61 -15 25 -15 -13 0 -55 -9 -94 -20 -90 -25 -95 -25 -95 3 0 37 19 48 75 42 27 -4 68 -8 89 -10z"></path> <path d="M1413 213 c-25 -9 -14 -44 17 -54 39 -14 39 -33 0 -27 -19 3 -29 1 -27 -6 6 -17 52 -19 66 -2 15 18 7 34 -25 46 -32 12 -31 30 2 30 14 0 23 4 19 10 -6 10 -31 12 -52 3z"></path> <path d="M1520 165 c0 -61 17 -76 22 -18 l3 37 25 -37 c14 -20 28 -37 33 -37 4 0 7 25 7 55 0 34 -4 55 -11 55 -7 0 -10 -14 -7 -35 2 -19 2 -35 -2 -35 -3 0 -16 16 -29 35 -13 19 -27 35 -32 35 -5 0 -9 -25 -9 -55z"></path> <path d="M1675 168 c-23 -49 -25 -84 -4 -45 13 22 55 22 68 0 5 -10 12 -15 16 -11 6 6 -41 108 -51 108 -3 0 -16 -23 -29 -52z m45 -4 c0 -8 -7 -14 -15 -14 -17 0 -18 2 -9 24 7 18 24 12 24 -10z"></path> <path d="M1807 202 c-9 -10 -17 -28 -17 -39 0 -27 33 -55 61 -51 35 5 33 23 -3 23 -30 0 -33 3 -33 30 0 27 3 30 33 30 37 0 38 19 1 23 -15 2 -32 -5 -42 -16z"></path> <path d="M1930 165 c0 -30 5 -55 10 -55 6 0 10 8 10 18 0 32 13 34 36 5 12 -16 25 -25 28 -22 4 3 -3 18 -15 33 l-21 27 23 25 c31 33 12 31 -23 -3 l-28 -27 0 27 c0 15 -4 27 -10 27 -5 0 -10 -25 -10 -55z"></path></g></svg></div>

                <div class="mt-8 bg-white dark:bg-gray-800 overflow-hidden shadow sm:rounded-lg">
                    <div class="grid grid-cols-1 md:grid-cols-2">
                        <div class="p-6">
                            <div class="flex items-center">
                                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500"><path d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path></svg>
                                <div class="ml-4 text-lg leading-7 font-semibold"><a href="https://laravel.com/docs" class="underline text-gray-900 dark:text-white">Inventory</a></div>
                            </div>

                            <div class="ml-12">
                                <div class="mt-2 text-gray-600 dark:text-gray-400 text-sm">
                                    Record all your coming in Inventory with item module, price modul, and storage module.
                                </div>
                            </div>
                        </div>

                        <div class="p-6 border-t border-gray-200 dark:border-gray-700 md:border-t-0 md:border-l">
                            <div class="flex items-center">
                                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500"><path d="M3 9a2 2 0 012-2h.93a2 2 0 001.664-.89l.812-1.22A2 2 0 0110.07 4h3.86a2 2 0 011.664.89l.812 1.22A2 2 0 0018.07 7H19a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2V9z"></path><path d="M15 13a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                                <div class="ml-4 text-lg leading-7 font-semibold"><a href="https://laracasts.com" class="underline text-gray-900 dark:text-white">Storage</a></div>
                            </div>

                            <div class="ml-12">
                                <div class="mt-2 text-gray-600 dark:text-gray-400 text-sm">
                                    Custom your storage module as detail as from branches, rooms, racks, section, and so on.
                                </div>
                            </div>
                        </div>

                        <div class="p-6 border-t border-gray-200 dark:border-gray-700">
                            <div class="flex items-center">
                                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500"><path d="M7 8h10M7 12h4m1 8l-4-4H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-3l-4 4z"></path></svg>
                                <div class="ml-4 text-lg leading-7 font-semibold"><a href="https://laravel-news.com/" class="underline text-gray-900 dark:text-white">Sales</a></div>
                            </div>

                            <div class="ml-12">
                                <div class="mt-2 text-gray-600 dark:text-gray-400 text-sm">
                                    Sales can be very intense, whether it is point of sales, coming out stocks, however you use it the application is as customeable as your Inventory flow.
                                </div>
                            </div>
                        </div>

                        <div class="p-6 border-t border-gray-200 dark:border-gray-700 md:border-l">
                            <div class="flex items-center">
                                <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" class="w-8 h-8 text-gray-500"><path d="M3.055 11H5a2 2 0 012 2v1a2 2 0 002 2 2 2 0 012 2v2.945M8 3.935V5.5A2.5 2.5 0 0010.5 8h.5a2 2 0 012 2 2 2 0 104 0 2 2 0 012-2h1.064M15 20.488V18a2 2 0 012-2h3.064M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                                <div class="ml-4 text-lg leading-7 font-semibold text-gray-900 dark:text-white">Reports</div>
                            </div>

                            <div class="ml-12">
                                <div class="mt-2 text-gray-600 dark:text-gray-400 text-sm">
                                    More than charts and numbers, Reports are designed to help you to make decisions, plans, and organize how the business model run.
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="flex justify-center mt-4 sm:items-center sm:justify-between">
                    <div class="text-center text-sm text-gray-500 sm:text-left">
                        <div class="flex items-center">
                            <svg fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" stroke="currentColor" class="-mt-px w-5 h-5 text-gray-400">
                                <path d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"></path>
                            </svg>

                            <a href="https://laravel.bigcartel.com" class="ml-1 underline">
                                Shop
                            </a>

                            <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" viewBox="0 0 24 24" class="ml-4 -mt-px w-5 h-5 text-gray-400">
                                <path d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"></path>
                            </svg>

                            <a href="https://github.com/sponsors/taylorotwell" class="ml-1 underline">
                                Point of Sales
                            </a>
                        </div>
                    </div>

                    <div class="ml-4 text-center text-sm text-gray-500 sm:text-right sm:ml-0">
                        Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .bg-gray-100 {
        background-color: #f7fafc;
        background-color: rgba(247, 250, 252, var(--tw-bg-opacity));
    }

    .border-gray-200 {
        border-color: #edf2f7;
        border-color: rgba(237, 242, 247, var(--tw-border-opacity));
    }

    .text-gray-400 {
        color: #cbd5e0;
        color: rgba(203, 213, 224, var(--tw-text-opacity));
    }

    .text-gray-500 {
        color: #a0aec0;
        color: rgba(160, 174, 192, var(--tw-text-opacity));
    }

    .text-gray-600 {
        color: #718096;
        color: rgba(113, 128, 150, var(--tw-text-opacity));
    }

    .text-gray-700 {
        color: #4a5568;
        color: rgba(74, 85, 104, var(--tw-text-opacity));
    }

    .text-gray-900 {
        color: #1a202c;
        color: rgba(26, 32, 44, var(--tw-text-opacity));
    }

    @media (prefers-color-scheme: dark) {
        .dark\:bg-gray-800 {
            background-color: #2d3748;
            background-color: rgba(45, 55, 72, var(--tw-bg-opacity));
        }

        .dark\:bg-gray-900 {
            background-color: #1a202c;
            background-color: rgba(26, 32, 44, var(--tw-bg-opacity));
        }

        .dark\:border-gray-700 {
            border-color: #4a5568;
            border-color: rgba(74, 85, 104, var(--tw-border-opacity));
        }

        .dark\:text-white {
            color: #fff;
            color: rgba(255, 255, 255, var(--tw-text-opacity));
        }

        .dark\:text-gray-400 {
            color: #cbd5e0;
            color: rgba(203, 213, 224, var(--tw-text-opacity));
        }
    }
</style>
