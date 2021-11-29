<template>
  
  <div id="watering-summary">

    <h2>Summary</h2>

    <h4>You have watered these plants</h4>

    <div v-if="watered">
        <p v-for="plant in watered" v-bind:key="plant.id">
            {{ plant.name }} has been watered.
        </p>
        </div>
    <div v-else class="empty-list-message">
        <p>No plants have been watered.</p>
    </div>


    <h4>You have NOT watered these plants</h4>

    <div v-if="notWatered"> 
        <p v-for="plant in notWatered" v-bind:key="plant.id">
            {{ plant.name }} needs to be watered.
        </p>
    </div>
    <div v-else class="empty-list-message">
        <p>All plants have been watered.</p>
    </div>

  </div>

</template>

<script>
export default {
  name: 'WateringSummary',
  props: {
      // TODO #6: Create a summary prop. The summary prop should be an Array.
  },
  computed: {
      watered() {
        // TODO #8: create a list of names of plants that have been watered. Use the summary prop
      },
      notWatered() {
        // TODO #9: create a list of names of plants that have NOT been watered. Use the summary prop         
      }
  }
    
}
</script>

<style>

.empty-list-message {
    font-style: italic;
}

#watering-summary {
    min-height: 20em;
}


</style>
