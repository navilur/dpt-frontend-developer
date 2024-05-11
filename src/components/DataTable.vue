<template>
  <div class="mx-auto overflow-x-scroll min-w-full">
    <table class="min-w-full leading-normal">
      <thead>
        <tr class="bg-gray-200">
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Flight
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Aircraft
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Class
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Fare
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Route
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Departure
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Arrival
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Duration
          </th>
          <th
            class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider"
          >
            Price
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(flight, index) in flights" :key="index" class="bg-white">
          <td class="px-6 py-4 whitespace-nowrap">
            <div
              v-for="segment in flight.itineraries[0].segments"
              :key="segment.id"
            >
              {{ segment.carrierCode }}
              {{ segment.flightNumber }}
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div
              v-for="segment in flight.itineraries[0].segments"
              :key="segment.id"
            >
              {{ segment.aircraft }}
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div v-for="fclasss in flight.class" :key="fclasss">
              <div v-for="fclass in fclasss" :key="fclass">
                {{ fclass }}
              </div>
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div v-for="fareBasiss in flight.class" :key="fareBasiss">
              <div v-for="fareBasis in fareBasiss" :key="fareBasis">
                {{ fareBasis }}
              </div>
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div
              v-for="segment in flight.itineraries[0].segments"
              :key="segment.id"
            >
              {{ segment.departure.iataCode }}-{{ segment.arrival.iataCode }}
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div
              v-for="segment in flight.itineraries[0].segments"
              :key="segment.id"
            >
              {{ segment.departure.at }}
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            <div
              v-for="segment in flight.itineraries[0].segments"
              :key="segment.id"
            >
              {{ segment.arrival.at }}
            </div>
          </td>
          <td class="px-6 py-4 whitespace-nowrap">
            {{ flight.itineraries[0].duration }}
          </td>
          <td class="px-6 py-4 whitespace-nowrap">{{ flight.price }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      flights: [],
      segments: "",
    };
  },
  mounted() {
    this.getFlight();
  },
  methods: {
    getFlight() {
      axios
        .get("/src/assets/data.json")
        .then((response) => {
          this.flights = response.data.flightOffer;
          console.log(this.flights);
        })
        .catch((error) => {
          console.error("Error fetching flight data:", error);
        });
    },
  },
};
</script>

<style></style>
