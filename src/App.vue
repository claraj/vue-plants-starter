<template>
  
  <h1>Houseplant Water Tracker</h1>

  <watering-summary
    todo="TODO #7: v-bind WateringSummary component's summary prop to App's wateringSummary computed property"
    />

  <plant-detail v-for="plant in plants" 
    v-bind:key="plant.id"
    todo1="TODO #2 v-bind the plant to the PlantDetail plant prop"
    todo2="TODO #5: v-on connect the water-update event to wateringUpdate method"
     />

</template>

<script>
import PlantDetail from './components/HousePlant.vue'
import WateringSummary from './components/WateringSummary.vue'

export default {
  name: 'App',
  components: {
    PlantDetail,
    WateringSummary
  },
  data() {
    return {
      plants: [
        { 
          id: 1,
          name: 'Elephant Ear Plant',
          description: 'Fast growing plant with decorative leaves.',
          wateringSchedule: 'weekly',
          photo: 'elephant_ear.jpeg',
          watered: false,
          lastWaterDate: null
        },
        { 
          id: 2,
          name: 'Snake Plant',
          description: 'Hardy houseplant with minimal water requirements.',
          wateringSchedule: 'monthly',
          photo: 'snake_plant.jpeg',
          watered: false,
          lastWaterDate: null
        },
        { 
          id: 3,
          name: 'Swiss Cheese Plant',
          description: 'Large houseplant with distinctive perforated leaves.',
          wateringSchedule: 'weekly',
          photo: 'swiss_cheese.jpeg',
          watered: false,
          lastWaterDate: null
        },

      ],
    }
  },
  computed: {
    wateringSummary() {
      let summary = [] 

      // optional TODO this could be replaced with a map statement
      this.plants.forEach( plant => {
        summary.push( {id: plant.id, name: plant.name, watered: plant.watered, lastWaterDate: plant.lastWaterDate } )
      })

      return summary 
    }
  },
  methods: {
    wateringUpdate(id, wasWatered, waterDate) {
      // find plant with this id, and update entry in wateringSummary
      let updatedPlant = this.plants.find( plant => plant.id == id)
      if (updatedPlant) {
        updatedPlant.watered = wasWatered
        if (wasWatered) {
          updatedPlant.lastWaterDate = waterDate
        } else {
          updatedPlant.lastWaterDate = null
        }
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
