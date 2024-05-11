<template>
  <div class="container mx-auto px-6">
    <h1 class="font-bold text-[28px]">Master Price</h1>
    <hr class="my-4" />
    <div
      class="flex border-t border-b border-[#818CF8] lg:justify-between flex-wrap gap-5 mb-5 py-3"
    >
      <div>
        <input
          type="text"
          class="h-10 w-[150px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        />
      </div>
      <div>
        <input
          type="text"
          class="h-10 w-[150px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        />
      </div>
      <div>
        <input
          type="date"
          class="h-10 w-[150px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        />
      </div>
      <div>
        <select
          class="h-10 w-[100px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        >
          <option>Day -</option>
        </select>
      </div>
      <div>
        <select
          class="h-10 w-[100px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        >
          <option>Day +</option>
        </select>
      </div>
      <div>
        <select
          class="h-10 w-[200px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        >
          <option>Any time</option>
        </select>
      </div>
      <div class="my-auto">+</div>
      <div>
        <select
          class="h-10 w-[100px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        >
          <option>ADT</option>
        </select>
      </div>
      <div>
        <select
          class="h-10 w-[100px] rounded-none border-[#6B7280] border bg-transparent py-0 pl-2 pr-7 text-gray-500 sm:text-sm"
        >
          <option>1</option>
        </select>
      </div>
      <div class="my-auto">+</div>
    </div>
    <div
      class="flex border-b border-[#818CF8] pb-3 justify-between flex-wrap gap-5 mb-5"
    >
      <div class="flex my-auto">
        <input
          type="checkbox"
          class="h-4 w-4 my-auto me-2 rounded-[5px]"
          id="checkbox"
        />
        <label for="checkbox" class="my-auto">Extra Options</label>
      </div>
      <div class="flex my-auto order-last md:order-none">
        <p class="my-auto me-4">Environment</p>
        <div class="me-4">
          <input
            type="radio"
            class="h-4 w-4 my-auto me-2 rounded-[5px]"
            id="radio1"
            name="env"
            checked
          />
          <label for="radio1" class="my-auto">Display value</label>
        </div>
        <div>
          <input
            type="radio"
            class="h-4 w-4 my-auto me-2 rounded-[5px]"
            id="radio2"
            name="env"
          />
          <label for="radio2" class="my-auto">Display value</label>
        </div>
      </div>
      <button
        class="btn bg-[#312E81] my-auto rounded-[5px] w-[100px] text-white p-3"
        @click="getFlight"
      >
        Search
      </button>
    </div>
    <data-table v-if="showTable" />
  </div>
</template>

<script>
import DataTable from "./DataTable.vue";
export default {
  components: { DataTable },
  data() {
    return {
      flights: [],
      showTable: false,
    };
  },
  methods: {
    getFlight() {
      this.showTable = true;
    },
  },
};
</script>

<style></style>
