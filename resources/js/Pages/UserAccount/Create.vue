<script setup>
import {Link, useForm} from "@inertiajs/vue3";

const form = useForm({
    name: null,
    email: null,
    password: null,
    password_confirmation: null
});
const register = () => form.post(route('user-account.store'));
</script>
<template>
    <form action="" @submit.prevent="register">
        <div class="w-1/2 mx-auto">
            <div>
                <label for="name" class="label">Your name</label>
                <input type="text" class="input" id="name" v-model="form.name"/>
                <div v-if="form.errors.name" class="input-error" >{{form.errors.name}}</div>
            </div>
            <div class="mt-4">
                <label for="email" class="label">E-mail (username)</label>
                <input type="text" class="input" id="email" v-model="form.email"/>
                <div v-if="form.errors.email" class="input-error" >{{form.errors.email}}</div>
            </div>
            <div class="mt-4">
                <label for="password" class="label">Password</label>
                <input type="password" class="input" id="password" v-model="form.password"/>
                <div v-if="form.errors.password" class="input-error" >{{form.errors.password}}</div>
            </div>
            <div class="mt-4">
                <label for="password_confirmation" class="label">Confirm Password</label>
                <input type="password" class="input" id="password_confirmation" v-model="form.password_confirmation"/>
                <div v-if="form.errors.password" class="input-error" >{{form.errors.password}}</div>
            </div>
            <div class="mt-4">
                <button class="btn-primary" type="submit">Create Account</button>
            </div>

            <div class="mt-2 text-center">
                <Link :href="route('login')" class="text-sm text-gray-500">Already have an account? Click here</Link>
            </div>
        </div>
    </form>
</template>
<style scoped>
</style>
