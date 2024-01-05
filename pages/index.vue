<script setup lang="ts">
const todos = ref([{ id: 0, title: "", description: "", status: false }]);

function handleDelete(id: number) {
  const data = [...todos.value];
  const filteredData = data.filter((item) => item.id !== id);
}

function handleAdd() {
  const data = [...todos.value];
}

function handleEdit(id: number) {
  const data = [...todos.value];
  const foundData = data.find((item) => item.id === id);
}
</script>

<template>
  <main class="w-full flex justify-center items-center">
    <section class="flex flex-col justify-center items-center max-w-5xl w-full">
      <div>
        <h1 class="text-2xl font-black">Todo App Vue</h1>
        <p>Sebuah todo list untuk belajar Nuxt JS saya</p>
        <form>
          <input
            v-model="todos[0].title"
            type="text"
            name="title"
            placeholder="Title...."
          />
          <input
            v-model="todos[0].description"
            type="text"
            name="description"
            placeholder="Description...."
          />
        </form>
        <p>{{ todos[0].title }}</p>
        <p>{{ todos[0].description }}</p>
      </div>
      <div class="mt-4">
        <div v-for="item in todos">
          <div class="border-2 border-black border-solid p-4">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>
