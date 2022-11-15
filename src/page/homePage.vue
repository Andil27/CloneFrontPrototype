<template>
  <div class="homePage">
    <RestaurantRow />
    <PagePost />
  </div>
</template>

<script>
//IMPORT
import BDD from "../BDD";
//COMPONENTS
import RestaurantRow from "../components/RestaurantRow.vue";
import PagePost from "../components/PagePost.vue";
export default {
  name: "HomePage",
  components: {
    RestaurantRow,
    PagePost,
  },
  setup() {
    console.log(BDD);
    class Restaurant {
      constructor(name, note, image, drive_time) {
        this.name = name;
        this.note = note;
        this.image = image;
        this.drive_time = drive_time;
      }
    }

    let data_restaurant = [];

    const makeDataRestaurant = () => {
      let three_restaurant = [];

      for (const restaurant of BDD) {
        const new_restaurant = new Restaurant(
          restaurant.name,
          restaurant.note,
          restaurant.image,
          restaurant.drive_time
        );

        three_restaurant.push(new_restaurant);

        if (three_restaurant.length === 3) {
          data_restaurant.push(three_restaurant);
          three_restaurant = [];
        }
      }

      console.log("data_restaurant :", data_restaurant);
    };
    makeDataRestaurant();
  },
};
</script>

<style></style>
