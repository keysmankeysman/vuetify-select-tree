<template>
  <div class="text-center">
    <v-select
      v-model="location"
      :items="locations"
      label="Location"
    ></v-select>
    <!-- <v-menu :location="location">
      <template v-slot:activator="{ props }">
        <v-btn
          color="primary"
          dark
          v-bind="props"
        >
          Dropdown
        </v-btn>
      </template>

      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu> -->
  </div>
</template>

<script>

export default {
    data: () => ({
      items: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],
      options: [ 
        {
          id: 'a',
          label: 'a',
          children: [ 
            {
              id: 'aa',
              label: 'aa',
              children: [ 
                {
                  id: 'zz',
                  label: 'zz',
                }
              ]
            }, 
            {
              id: 'ab',
              label: 'ab',
            } 
          ],
        }, 
        {
          id: 'b',
          label: 'b',
        }, 
        {
          id: 'c',
          label: 'c',
        } 
      ],
      locations: [
        'top',
        'bottom',
        'start',
        'end',
        'center',
      ],
      location: 'end',
    }),
  }

</script>

<style scoped>

.inner {
  margin-left: ;
}

</style>