<template>
  <div class="p-2">
    <div @click.capture="navFn">
      <form class="flex flex-col gap-2">
        <input
          type="submit"
          @click.prevent="submitFn"
          value="Submit"
          class="w-36 bg-blue-500 text-white rounded-lg p-2"
        />
        <input
          type="button"
          @click="clearFn"
          value="Clear"
          class="w-36 bg-blue-500 text-white rounded-lg p-2"
        />
      </form>
    </div>
    <div v-html="state.action"></div>
  </div>
</template>

<script lang="ts">
import { reactive } from "vue";

export default {
  name: "TestTwo",
  setup() {
    const state = reactive({
      action: "",
    });
    function submitFn() {
      state.action += "表單送出<br>";
    }
    function navFn() {
      state.action += "選單點選<br>";
    }
    function clearFn() {
      state.action = "";
    }
    return { state, submitFn, clearFn, navFn };
  },
};
</script>
