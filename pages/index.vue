<template>
  <main>
    <section class="text-center pt-2 px-2">
      <h1 class="font-bold text-4xl">ToDos</h1>
      <p>Write your task!</p>
    </section>
    <section class="flex justify-center mt-4">
      <input
        type="text"
        class="border border-neutral-500 rounded-lg p-2"
        placeholder="entry your task!"
        @focusout="addTodo"
      />
    </section>
    <section class="px-2 mt-5 flex flex-col gap-y-3">
      <div
        class="bg-neutral-200 rounded-md px-3 py-4 flex"
        v-for="(items, index) in task"
        :id="index"
      >
        <p class="font-medium">{{ items.todo }}</p>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      task: [],
    };
  },
  methods: {
    addTodo(e) {
      if (!e.target.value) return;
      this.task.push({
        todo: e.target.value,
        status: "active",
      });
      e.target.value = "";
    },
  },
};
</script>
