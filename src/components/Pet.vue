<template>
  <div class="pet">
    <Card>
      <template #header>
        <img
          :src="pet.url"
          alt="Pet"
        />
      </template>
      <template #title> {{ pet.name }} </template>
      <template #subtitle> {{ pet.age }} </template>
      <!-- <template #content>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore
          sed consequuntur error repudiandae numquam deserunt quisquam repellat
          libero asperiores earum nam nobis, culpa ratione quam perferendis
          esse, cupiditate neque quas!
        </p>
      </template> -->
      <template #footer>
        <Button
          icon="pi pi-times"
          @click="onRemove(pet.id)"
          label="Remove"
          class="p-button-danger"
          style="margin-right: 4em"
        />
        <Button
          icon="pi pi-heart"
          @click="$emit('add-favorite', pet.id)"
          :class="[
            pet.isFavorite ? '' : 'p-button-outlined',
            'p-button-rounded',
            'p-button-danger',
          ]"
        />
      </template>
    </Card>
  </div>
</template>

<script>
export default {
  props: {
    pet: Object,
  },
  components: {},
  methods: {
    onRemove(id) {
      //console.log("id: ", id)
      this.$emit("remove-pet", id);
    },
  },
};
</script>

<style>
</style>