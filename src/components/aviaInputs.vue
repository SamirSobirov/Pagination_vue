<template>
  <div class="flex items-center justify-center">
    <div
      class="mt-[20px] h-[200px] w-[80%] bg-[#5941d3] rounded-xl flex gap-1 items-center justify-center"
    >
      <div ref="dropdownWrapper" class="relative w-[300px]">
        <input
          v-model="fromAirport"
          @focus="showDropdown = true"
          @input="filterAirports"
          @click.stop="showDropdown = true"
          class="pl-4 pr-[50px] py-2 rounded-lg w-full h-[50px] border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500"
          type="text"
          placeholder="Откуда"
        />
        <div
          v-if="showDropdown && filteredAirports.length"
          class="absolute max-h-[200px] overflow-y-auto left-0 mt-2 bg-white border border-gray-300 rounded-lg shadow-lg w-[400px] z-10"
        >
          <ul>
            <li
              v-for="(airport, index) in filteredAirports"
              :key="index"
              class="px-4 py-2 hover:bg-gray-100 cursor-pointer"
              @click="selectAirport(airport)"
            >
              {{ airport.city_rus }} ({{ airport.iata_code }}) -
              {{ airport.name_rus }}
            </li>
          </ul>
        </div>
        <span
          class="absolute inset-y-0 right-4 flex items-center text-gray-500 pointer-events-none"
        >
          {{ fromAirportCode }}
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
import axios from "axios";

export default {
  name: "aviaInputs",
  data() {
    return {
      showDropdown: false,
      fromAirport: "",
      fromAirportCode: "SKD",
      airports: [],
      filteredAirports: [],
    };
  },
  methods: {
    async fetchAirports() {
      try {
        const response = await axios.get(
          "https://api2.globaltravel.space/static/airports"
        );
        this.airports = response.data.data;
        this.filteredAirports = this.airports;
      } catch (error) {
        console.error("Error fetching airports:", error);
      }
    },
    filterAirports() {
      const query = this.fromAirport.toLowerCase();
      this.filteredAirports = this.airports.filter((airport) =>
        airport.city_rus.toLowerCase().startsWith(query)
      );
    },
    selectAirport(airport) {
      this.fromAirport = airport.city_rus;
      this.fromAirportCode = airport.iata_code;
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






