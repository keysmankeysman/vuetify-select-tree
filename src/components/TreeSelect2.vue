<template>
  <v-container class="fill-height">
    <div class="d-flex justify-space-around">
      TreeSelect2
      <v-menu>
        <template v-slot:activator="{ props }">
          <v-btn
            color="primary"
            v-bind="props"
          >
            {{ currentValue }}
          </v-btn>
        </template>

        <v-treeview :items="options"></v-treeview>

        <!-- <v-select
          label="Select"
          :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
        ></v-select> -->

        <!-- <v-list>
          <v-list-item
            v-for="(item, index) in options"
            :key="index"
            :value="index"
          >
            <v-list-item-title @click="onClick(item)">{{ item.label }}</v-list-item-title>
            <v-list-item
              v-for="(item1, index) in item.children"
              v-if="item.children"
              :key="index"
              :value="index"
            >
              <v-list-item-title @click="onClick(item)">{{ item1.label }}</v-list-item-title>
              <v-list-item
                v-for="(item2, index) in item.children"
                v-if="item1.children"
                :key="index"
                :value="index"
              >
                <v-list-item-title @click="onClick(item)">{{ item2.label }}</v-list-item-title>
              </v-list-item>
            </v-list-item>

            
          </v-list-item>
        </v-list> -->

        <!-- <v-list>
          <div
            v-for="(item, index) in options"
            :key="index"
            :value="index"
          >
            <div @click="onClick(item)">{{ item.label }}</div>
            <div 
              
              v-for="(item1, index) in item.children"
              v-if="item.children"
              :key="index"
              :value="index"
              class="inner"
            >
              <div>{{ item1.label }}</div>
              <div
                v-for="(item2, index) in item.children"
                v-if="item1.children"
                :key="index"
                :value="index"
                class="inner"
              >
                <div>{{ item2.label }}</div>
              </div>
            </div>

            
          </div>
        </v-list> -->

        <!-- <v-list>
          <div
            v-for="(item, index) in options"
            :key="index"
          >
            {{ item.label }}
            <div 
              v-if="item.children"
              v-for="(itemChild, index) in item.children"
            :key="index"
            >
              {{ itemChild.label }}
            </div>
          </div>
        </v-list> -->
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
      currentValue: 'Пример',
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


    }),
    methods: { 
      onClick(item) {
        console.log('item', item)
      }
    }
  }
</script>

<style scoped>

.inner {
  margin-left: 8px;
}

</style>