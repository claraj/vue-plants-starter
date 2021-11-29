<template>
  <div class="plant-detail">

    <div class="plant-container">

      <div class="plant-text">
      <h2>{{ plant.name }}</h2>

      <h3>Watering Schedule</h3>

      <p>{{ plant.description }}</p>
      <p>You should water this plant <b>{{ plant.wateringSchedule }}.</b></p>

      <p v-if="plant.lastWaterDate">Last water date: {{ shortDate(plant.lastWaterDate) }}</p>
      <p v-else>Last water date: unknown</p>

      <label>Have you watered this plant?</label>
      <input type="checkbox" v-model="userSetWatered" v-on:change="waterUpdate">

    </div>

    <div class="plant-image">   
      <img v-bind:src="photoPath(plant.photo)">
    </div> 

  </div>

  <hr>

  </div>
</template>

<script>
export default {
  name: 'HousePlant',
  // TODO #4: specify this component emits a water-update event
  props: {
    // TODO #2: create a plant prop. This prop is an Object
  },
  data() {
    return {
      // TODO #2b: create a userSetWatered data. The value will be set from the plant props watered property
    }
  },
  methods: {
    waterUpdate() {
      let dateWatered = new Date()
      // TODO #3: emit 'water-update' message with the plant's id, if it is watered, the dateWatered 

    },
    photoPath(imageFile) {
      // dynamically set image path.  @ is shorthand for your vue folder's src directory.
      return require('@/assets/' + imageFile)
    },
    shortDate(date) {
      if (date) {
        return new Intl.DateTimeFormat('en-US', {timeZone: 'UTC'}).format(date)
      }
    }
  }

}
</script>

<style scoped>

.plant-container {
  /* Flexbox - display text and image on one line, and wrap as needed
  https://css-tricks.com/snippets/css/a-guide-to-flexbox/ */
  display: flex;
  justify-content: space-evenly;
  align-content: stretch;
  flex-wrap: wrap;
}

.plant-text {
  flex-grow: 2;   /** take up twice as much space as the plant-image */
}

.plant-image {
  flex-grow: 1;
}

</style>
