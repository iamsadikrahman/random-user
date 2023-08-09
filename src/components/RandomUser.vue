<script setup>
import { reactive, ref, onMounted } from "vue";

const persons = reactive([
  {
    image: "https://i.pravatar.cc/150?img=1",
    name: "Emmie Dufour",
    email: "emmie@example.com",
    age: "22",
    address: "Dhaka",
    phone: "011016-7000111",
    password: "dufour22",
  },
  {
    image: "https://i.pravatar.cc/150?img=2",
    name: "Sasha Mcdonough",
    email: "sasha@example.com",
    age: "28",
    address: "New York",
    phone: "012345-6789000",
    password: "mcdonough28",
  },
  {
    image: "https://i.pravatar.cc/150?img=3",
    name: "Kian Ferreira",
    email: "kian@example.com",
    age: "35",
    address: "London",
    phone: "023456-7890111",
    password: "ferreira35",
  },
  {
    image: "https://i.pravatar.cc/150?img=4",
    name: "Selena Whitaker",
    email: "selena@example.com",
    age: "40",
    address: "Los Angeles",
    phone: "034567-8901222",
    password: "whitaker40",
  },
  {
    image: "https://i.pravatar.cc/150?img=5",
    name: "Luka Singleton",
    email: "luka@example.com",
    age: "26",
    address: "Paris",
    phone: "045678-9012333",
    password: "singleton26",
  },
  {
    image: "https://i.pravatar.cc/150?img=6",
    name: "Elin Rogers",
    email: "elin@example.com",
    age: "32",
    address: "Stockholm",
    phone: "056789-0123444",
    password: "rogers32",
  },
  {
    image: "https://i.pravatar.cc/150?img=7",
    name: "Adrien Graves",
    email: "adrien@example.com",
    age: "23",
    address: "Berlin",
    phone: "067890-1234555",
    password: "graves23",
  },
  {
    image: "https://i.pravatar.cc/150?img=8",
    name: "Mara Patel",
    email: "mara@example.com",
    age: "29",
    address: "Mumbai",
    phone: "078901-2345666",
    password: "patel29",
  },
  {
    image: "https://i.pravatar.cc/150?img=9",
    name: "Davion Franco",
    email: "davion@example.com",
    age: "45",
    address: "Barcelona",
    phone: "089012-3456777",
    password: "franco45",
  },
  {
    image: "https://i.pravatar.cc/150?img=10",
    name: "Zahra Bautista",
    email: "zahra@example.com",
    age: "31",
    address: "Mexico City",
    phone: "090123-4567888",
    password: "bautista31",
  },
]);

let index = ref(0);
let allKeys = ref("");
let allValues = ref("");
let infoButtonIndex = ref(1);

function getRandomUser() {
  index.value = Math.floor(Math.random() * persons.length);
  allKeys.value = Object.keys(persons[index.value]);
  allValues.value = Object.values(persons[index.value]);
}

onMounted(() => {
  allKeys.value = Object.keys(persons[index.value]);
  allValues.value = Object.values(persons[index.value]);
  console.log(allKeys.value);
  console.log(allValues.value);
});
</script>

<template>
  <section class="h-screen bg-slate-400 flex justify-center items-center w-full">
    <div
      class="flex flex-col space-y-5 justify-center items-center border p-20 rounded-lg bg-pink-900 text-white mx-5"
    >
      <img class="w-32 rounded-full" :src="allValues[0]" alt="" />
      <div class="text-2xl flex flex-col space-y-2 justify-center items-center">
        <h2>My {{ allKeys[infoButtonIndex] }} is</h2>
        <h2 class="font-bold">{{ allValues[infoButtonIndex] }}</h2>
      </div>
      <div class="flex space-x-5">
        <i @click="infoButtonIndex = 1" class="material-icons text-4xl cursor-pointer"
          >person</i
        >
        <i @click="infoButtonIndex = 2" class="material-icons text-4xl cursor-pointer"
          >email</i
        >
        <i @click="infoButtonIndex = 3" class="material-icons text-4xl cursor-pointer"
          >calendar_month</i
        >
        <i @click="infoButtonIndex = 4" class="material-icons text-4xl cursor-pointer"
          >home</i
        >
        <i @click="infoButtonIndex = 5" class="material-icons text-4xl cursor-pointer"
          >phone</i
        >
        <i @click="infoButtonIndex = 6" class="material-icons text-4xl cursor-pointer"
          >password</i
        >
      </div>
      <small class="italic">*click these icons to get specific info</small>
      <button
        @click="getRandomUser"
        class="text-2xl bg-yellow-300 rounded-lg font-semibold px-5 py-2 text-black"
      >
        Random User
      </button>
    </div>
  </section>
</template>

<style scoped></style>
