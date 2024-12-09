<template>
  <div class="flex items-center justify-center">
    <div
      class="mt-[20px] h-[200px] w-[80%] bg-[#5941d3] rounded-xl flex gap-1 items-center justify-center"
    >
    <div ref="dropdownWrapper" class="relative w-[300px]">
    <input
      @focus="showDropdown = true"
      @click.stop="showDropdown = true"
      class="pl-4 pr-[50px] py-2 rounded-lg w-full h-[50px] border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500"
      type="text"
      placeholder="Откуда"
    />
    <div
      v-if="showDropdown"
      class="absolute h-[400px] left-0 mt-2 bg-white border border-gray-300 rounded-lg shadow-lg w-[400px] z-10"
    >
      <ul>
        <li
          v-for="(item, index) in dropdownItems"
          :key="index"
          class="px-4 py-2 hover:bg-gray-100 cursor-pointer"
          @click="selectItem(item)"
        >
          {{ item }}
        </li>
      </ul>
    </div>
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
import axios from "axios";

export default {
  name: "aviaInputs",
  data() {
    return {
      showDropdown: false,
      fromAirport: "",
      toAirport: "",
      fromAirportCode: "SKD",
      toAirportCode: "",
      airports: [], 
    };
  },
  computed: {
    filteredAirports() {
      return this.airports.filter((airport) =>
        airport.name.toLowerCase().includes(this.fromAirport.toLowerCase())
      );
    },
  },
  methods: {
    selectAirport(airport) {
      this.fromAirport = airport.name;
      this.fromAirportCode = airport.code;
      this.showDropdown = false;
    },
  
    handleClickOutside(event) {
      if (
        this.$refs.dropdownWrapper &&
        !this.$refs.dropdownWrapper.contains(event.target)
      ) {
        this.showDropdown = false;
      }
    },

    async fetchAirports() {
      try {
        const response = await axios.get(
          "https://api2.globaltravel.space/static/airports"
        );
        this.airports = response.data;
      } catch (error) {
        console.error("Error fetching airports:", error);
      }
    },
  },
  mounted() {
    this.fetchAirports();

    document.addEventListener("click", this.handleClickOutside);
  },
  beforeDestroy() {
    document.removeEventListener("click", this.handleClickOutside);
  },
};
</script>

<style scoped></style>