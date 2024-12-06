<template>
  <div class="flex flex-col">
    <div
      v-for="tour in paginatedTours"
      :key="tour.id"
      class="flex w-[1100px] justify-between items-center p-4"
    >
      <div class="flex gap-[16px]">
        <p class="text-[#475569]">ID: {{ tour.id }}</p>
        <p>{{ tour.name }}</p>
      </div>

      <div class="flex gap-[26px]">
        <p>USD</p>
        <p>{{ tour.price }}</p>
      </div>

      <div class="flex gap-[12px]">
        <img src="../../public/icons/plane_icon.svg" alt="Plane Icon" />
        <p>Авиа</p>
      </div>

      <div class="flex">
        <p>{{ tour.date }}</p>
      </div>
    </div>

    <div
      v-if="totalPages > 1"
      class="flex w-[1100px] justify-between items-center p-4"
    >
      <button
        class="flex border items-center gap-4 border-[#475569] rounded-3xl px-4 py-2"
        @click="togglePerPage"
      >
        <p class="text-[#475569]">
          {{ itemsPerPage === 5 ? "Показать всё" : "Показать по 5" }}
        </p>
        <img src="../../public/icons/Arrow-Down2.svg" alt="" />
      </button>

      <div class="flex gap-4 items-center justify-center text-center">
        <button :disabled="currentPage === 1" @click="prevPage">
          <img src="../../public/icons/ArrowLeft-Outline.svg" alt="" />
        </button>
        <button
          v-for="page in totalPages"
          :key="page"
          :class="{
            'font-bold underline': currentPage === page,
          }"
          @click="goToPage(page)"
        >
          {{ page }}
        </button>
        <button :disabled="currentPage === totalPages" @click="nextPage">
          <img
            class="rotate-180"
            src="../../public/icons/ArrowLeft-Outline.svg"
            alt=""
          />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tours: [
        { id: "1", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "2", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "3", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "4", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "5", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "6", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "7", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "8", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "9", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "10", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "11", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "12", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
        { id: "13", name: "ELBEK TRAVEL", price: "3.000", date: "Авг 5, 2022" },
      ],
      currentPage: 1,
      itemsPerPage: 5,
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.tours.length / this.itemsPerPage);
    },
    paginatedTours() {
      const start = (this.currentPage - 1) * this.itemsPerPage;
      const end = start + this.itemsPerPage;
      return this.tours.slice(start, end);
    },
  },
  methods: {
    goToPage(page) {
      this.currentPage = page;
    },
    nextPage() {
      if (this.currentPage < this.totalPages) {
        this.currentPage++;
      }
    },
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
    togglePerPage() {
      if (this.itemsPerPage === 5) {
        this.itemsPerPage = this.tours.length;
      } else {
        this.itemsPerPage = 5;
        this.currentPage = 1;
      }
    },
  },
};
</script>
