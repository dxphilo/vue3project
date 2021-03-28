<template>
  <div class="addemail">
    <div class="text-center pt-32 bg-gray-500 pb-20">
      <h1 class="text-5xl">Add Email</h1>
      <p class="text-2xl pt-10">Enter your email</p>
      <form @submit.prevent="getMail" class="pt-6">
        <input
          type="email"
          v-model="email"
          placeholder="Enter your email ..."
          class="py-2 px-7 focus:outline-none"
        />
        <button
          class="py-2 px-7 bg-green-400 hover:bg-green-500 focus:outline-none"
          type="submit"
        >
          Submit
        </button>
      </form>
    </div>
    <div v-for="email in emailS" :key="email" class="w-64 mx-auto pt-2">
      <h1
        class="text-2xl text-center py-1 px-10 bg-green-400 mb-1 border-yellow-400"
      >
        {{ email }}
      </h1>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "App",
  setup() {
    let email = ref("");

    let emailS = ref([]);

    function getMail() {
      emailS.value.push(email.value);
      email.value = "";
      console.log(emailS);
    }

    return { email, emailS, getMail };
  },
};
</script>

<style>
</style>
