<template>
  <div class="flex items-center justify-center">
    <div
      class="mt-[64px] h-[200px] w-[80%] bg-[#5941d3] rounded-xl flex gap-1 items-center justify-center"
    >
      <div class="relative w-[300px]">
        <input
          class="pl-4 pr-[50px] py-2 rounded-lg w-full h-[50px] border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500"
          type="text"
          placeholder="Откуда"
        />
        <span
          class="absolute inset-y-0 right-4 flex items-center text-gray-500 pointer-events-none"
        >
          SKD
        </span>
      </div>

      <input
        class="pl-4 pr-[50px] py-2 rounded-lg w-[220px] h-[50px] border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500"
        type="text"
        placeholder="Куда"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "aviaInputs",
};
</script>

<style scoped></style>
