<template>
    <div class="relative bg-white">
        <div class="max-w-7xl mx-auto px-4 sm:px-6">
            <div class="flex justify-between items-center border-b-2 border-gray-100 py-6 md:justify-start md:space-x-10">
                <div class="lg:w-0 lg:flex-1">
                    <a href="#" class="flex">
                        <img class="h-8 w-auto sm:h-10" src="https://www.hospitad.com/assets/img/brand.svg" alt="Hospitad" />
                    </a>
                </div>
                <div class="-mr-2 -my-2 md:hidden">
                    <button type="button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
                        <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
                        </svg>
                    </button>
                </div>
                <div v-if="user == null" class="hidden md:flex items-center justify-end space-x-8 md:flex-1 lg:w-0">
                    <router-link :to="{ name: 'login' }" class="whitespace-no-wrap text-base leading-6 font-medium text-gray-500 hover:text-gray-900 focus:outline-none focus:text-gray-900">Sign in</router-link>
                    <span class="inline-flex rounded-md shadow-sm">
                        <router-link :to="{ name: 'register' }" class="whitespace-no-wrap inline-flex items-center justify-center px-4 py-2 border border-transparent text-base leading-6 font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-500 focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo active:bg-indigo-700 transition ease-in-out duration-150">
                            Sign up
                        </router-link>
                    </span>
                </div>
                <div v-else class="hidden md:flex items-center justify-end space-x-8 md:flex-1 lg:w-0">
                    <span>{{ user.name }}</span>
                    <span class="inline-flex rounded-md shadow-sm">
                        <router-link :to="{ name: 'logout' }" class="whitespace-no-wrap inline-flex items-center justify-center px-4 py-2 border border-transparent text-base leading-6 font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-500 focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo active:bg-indigo-700 transition ease-in-out duration-150">
                            Logout
                        </router-link>
                    </span>
                </div>
            </div>
        </div>
        <div class="absolute top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden">
            <div class="rounded-lg shadow-lg">
                <div class="rounded-lg shadow-xs bg-white divide-y-2 divide-gray-50">
                    <div class="pt-5 pb-6 px-5 space-y-6">
                        <div class="flex items-center justify-between">
                            <div>
                                <img class="h-8 w-auto" src="https://www.hospitad.com/assets/img/brand.svg" alt="Hospitad" />
                            </div>
                            <div class="-mr-2">
                                <button type="button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out">
                                    <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
                                    </svg>
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="py-6 px-5 space-y-6">
                        <div class="space-y-6">
                            <span class="w-full flex rounded-md shadow-sm">
                                <router-link :to="{ name: 'register' }" class="w-full flex items-center justify-center px-4 py-2 border border-transparent text-base leading-6 font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-500 focus:outline-none focus:border-indigo-700 focus:shadow-outline-indigo active:bg-indigo-700 transition ease-in-out duration-150">
                                    Sign up
                                </router-link>
                            </span>
                            <p class="text-center text-base leading-6 font-medium text-gray-500">
                                Existing user?
                                <router-link :to="{ name: 'login' }" class="text-indigo-600 hover:text-indigo-500 transition ease-in-out duration-150">
                                    Sign in
                                </router-link>
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        computed: {
            user () {
                return this.$store.state.user
            }
        }
    }
</script>
