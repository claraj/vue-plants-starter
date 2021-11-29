## Example Vue Project for setting props and emitting events

Works with objects that store data about houseplants.  

### Image Credits 

Elephant Ear Plant Photo by <a href="https://unsplash.com/@sannisahil?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Sanni Sahil</a> on <a href="https://unsplash.com/s/photos/houseplants?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  

Swiss Cheese Plant Photo by <a href="https://unsplash.com/@anniespratt?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Annie Spratt</a> on <a href="https://unsplash.com/s/photos/houseplants?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  

Snake Plant Photo by <a href="https://unsplash.com/@jakegoossen?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Jake Goossen</a> on <a href="https://unsplash.com/s/photos/snake-plant?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  
### Extra Credit

Add a datetime-local input to the HousePlant component. (https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/datetime-local) You'll need to add a new data and use v-model so the Vue code can read the value. 

When the user indicates the plant has been watered by checking the checkbox, ensure they enter a date that the plant was watered. Instead of emitting the current  date and time, emit the datetime the user watered the plant.

Modify App.vue's wateringSummary computed property and include the wateringSchedule property for each plant.

In WateringSummary, instead of plants that are watered and not watered, display a list of plants who have been watered recently, and plants who have not been watered, or not watered recently enough.  

For example, if today is March 10th 2021, and we have a plant who has a weekly wateringSchedule. If this plant was last watered on February 1st 2021, it is overdue for watering.  If this plant was last watered on March 8th 2021 it is not overdue.   If this plant has never been watered, it's overdue for watering. 

Use the last watered date, and the wateringSchedule, to display a warning for any plants who have never been watered, and for plants that are overdue for watering.  

You may assume that every month is 30 days long. 

*Hint* One solution to decide if a plant is overdue, is to convert the current date and the last watered date to times in milliseconds, determine the difference between these two numbers of milliseconds, and decide if that is more than one week or one month.  One week is 1000 * 60 * 60 * 24 * 7 milliseconds long.  (milliseconds in a second * seconds in a minutes * minutes in an hour * hours in a day * days in a week). 