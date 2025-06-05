<script setup>
import { Head, Link } from "@inertiajs/vue3";

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Welcome" />
    <div
        class="relative w-full max-w-md mx-auto mt-20 bg-white dark:bg-neutral-900 shadow-lg rounded-2xl px-6 py-10"
    >
        <h1
            class="text-3xl font-bold text-center text-black dark:text-white mb-6"
        >
            Welcome to CJLF Network
        </h1>
        <p class="text-center text-sm text-gray-500 dark:text-gray-400 mb-8">
            Login to access the internet
        </p>

        <div v-if="canLogin" class="flex flex-col space-y-4">
            <Link
                :href="route('login')"
                class="w-full rounded-lg bg-[#FF2D20] px-4 py-2 text-white font-medium hover:bg-red-600 transition"
            >
                Log in
            </Link>
            <Link
                v-if="canRegister"
                :href="route('register')"
                class="w-full rounded-lg border border-[#FF2D20] text-[#FF2D20] px-4 py-2 font-medium hover:bg-[#FF2D20]/10 transition"
            >
                Register
            </Link>
        </div>
    </div>
</template>
