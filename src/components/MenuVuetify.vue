<template>
  <v-container class="fill-height">
    <div class="d-flex justify-space-around">
      <v-menu>
        <template v-slot:activator="{ props }">
          <v-btn
            color="primary"
            v-bind="props"
          >
            Открыть меню
          </v-btn>
        </template>
        <v-list>
          <v-list-item
            v-for="(item, index) in options"
            :key="index"
            :value="index"
          >
            <v-list-item-title @click="onClick(item)">{{ item.label }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

    </div>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      menuItems: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' },
      ],

      options: [ 
        {
          id: 'a',
          label: 'a',
          children: [ {
            id: 'aa',
            label: 'aa',
          }, {
            id: 'ab',
            label: 'ab',
          } ],
        }, {
          id: 'b',
          label: 'b',
        }, {
          id: 'c',
          label: 'c',
        } 
      ],


    }),
    methods: { 
      onClick(item) {
        console.log('item', item)
      }
    }
  }
</script>
