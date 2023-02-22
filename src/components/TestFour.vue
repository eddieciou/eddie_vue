<template>
  <div class="p-2 flex flex-col gap-2">
    <p>
      <select
        v-model="state.type"
        class="outline-none p-2 w-36 text-center border border-blue-500 rounded-lg"
      >
        <option
          v-for="item in state.types"
          :key="item.value"
          :value="item.value"
        >
          {{ item.title }}
        </option>
      </select>
    </p>
    <p>
      <select
        v-model="state.name"
        class="outline-none p-2 w-36 text-center border border-blue-500 rounded-lg"
      >
        <option
          v-for="item in state.names"
          :key="item.value"
          :value="item.value"
        >
          {{ item.title }}
        </option>
      </select>
    </p>
    <p>Type: {{ state.type }}</p>
    <p>Framework: {{ state.name }}</p>
  </div>
</template>

<script>
import { reactive } from "vue";

export default {
  name: "TestFour",
  setup() {
    const state = reactive({
      type: "Frontend",
      name: "Vue",
      names: [
        { title: "Vue", value: "Vue" },
        { title: "React", value: "React" },
        { title: "Angular", value: "Angular" },
        { title: "Laravel", value: "Laravel" },
        { title: "CakePHP", value: "CakePHP" },
        { title: "Django", value: "Django" },
      ],
      types: [
        { title: "Frontend", value: "Frontend" },
        { title: "Backend", value: "Backend" },
      ],
    });

    return { state };
  },
};
</script>
