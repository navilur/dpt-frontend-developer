<template>
  <div class="bg-[#1F2937] mb-2">
    <div class="font-sans antialiased container mx-auto" id="app">
      <nav class="flex items-center justify-between flex-wrap bg-teal p-6">
        <div class="block sm:hidden text-white mr-6">
          <span class="font-semibold text-xl tracking-tight">Dashboard</span>
        </div>
        <div class="block sm:hidden">
          <button
            @click="toggle"
            class="flex items-center px-3 py-2 border rounded border-teal-light text-white border-white"
          >
            <svg
              class="fill-current h-3 w-3"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Menu</title>
              <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
            </svg>
          </button>
        </div>
        <div
          :class="open ? 'block' : 'hidden'"
          class="w-full flex-grow sm:flex sm:items-center sm:w-auto"
        >
          <div class="text-sm sm:flex-grow">
            <a
              href="#responsive-header"
              class="no-underline block mt-4 sm:inline-block sm:mt-0 text-white mr-4"
            >
              Dashboard
            </a>
            <a
              href="#responsive-header"
              class="no-underline block mt-4 sm:inline-block sm:mt-0 text-white mr-4"
            >
              Master Price
            </a>
            <a
              href="#responsive-header"
              class="no-underline block mt-4 sm:inline-block sm:mt-0 text-white mr-4"
            >
              Custom Price
            </a>
            <a
              href="#responsive-header"
              class="no-underline block mt-4 sm:inline-block sm:mt-0 text-white mr-4"
            >
              Calender
            </a>
            <a
              href="#responsive-header"
              class="no-underline block mt-4 sm:inline-block sm:mt-0 text-white"
            >
              Report
            </a>
          </div>
          <div></div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      open: false,
    };
  },
  methods: {
    toggle() {
      this.open = !this.open;
    },
  },
};
</script>

<style></style>
