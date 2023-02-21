<template>
  <div class="p-2 flex flex-col gap-2">
    <p>
      <select
        @change="changeValue($event, 'type')"
        v-model="framework.type"
        class="outline-none p-2 w-36 text-center border border-blue-500 rounded-lg"
      >
        <option value="Frontend">Frontend</option>
        <option value="Backend">Backend</option>
      </select>
    </p>
    <p>
      <select
        @change="changeValue($event, 'name')"
        v-model="framework.name"
        class="outline-none p-2 w-36 text-center border border-blue-500 rounded-lg"
      >
        <option value="Vue">Vue</option>
        <option value="React">React</option>
        <option value="Angular">Angular</option>
        <option value="Laravel">Laravel</option>
        <option value="CakePHP">CakePHP</option>
        <option value="Django">Django</option>
      </select>
    </p>
    <p>Type: {{ framework.type }}</p>
    <p>Framework: {{ framework.name }}</p>
  </div>
</template>

<script lang="ts">
import { reactive } from "vue";
export default {
  name: "app",
  setup() {
    const framework = reactive({
      type: "Frontend",
      name: "Vue",
    });

    const changeValue = (e: Event, id: "type" | "name") => {
      framework[id] = (e.target as HTMLSelectElement).value;
    };

    return { framework, changeValue };
  },
};
</script>
