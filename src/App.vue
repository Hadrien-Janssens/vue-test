<script setup lang="ts">
import Layout from "./components/Layout.vue";
import Button from "./components/Button.vue";
import { ref } from "vue";

const taches = ref(["Tache 1", "Tache 2", "Tache 3"]);
const newTask = ref("");

const addTask = () => {
  taches.value.push(newTask.value);
  newTask.value = "";
};
</script>

<template>
  <Layout>
    <template v-slot:title>
      <h1 class="mt-5 text-3xl font-bold">Liste de tâches</h1>
    </template>

    <template v-slot:content>
      <input
        type="text"
        placeholder="ajouter un tâche"
        class="border rounded-md p-1"
        v-model="newTask"
      />
      <Button @click="addTask">Ajouter</Button>
      <ul>
        <li
          class="my-4 border max-w-48 flex justify-between items-center p-1 rounded-md"
          v-for="tache in taches"
        >
          {{ tache }} <input type="checkbox" name="" id="" />
          <button class="bg-red-500 text-white rounded px-1">Supprimer</button>
        </li>
      </ul>
    </template>
  </Layout>
</template>
