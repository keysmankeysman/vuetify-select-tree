<template>
  <v-container>
    <v-select v-model="selectionType" :items="['leaf', 'independent']" label="Selection type"></v-select>
    <v-row>
      <v-col>
        <v-treeview
          v-model="selection"
          :items="items"
          :selection-type="selectionType"
          selectable
          return-object
          open-all
        ></v-treeview>
      </v-col>
      <v-divider vertical></v-divider>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    selectionType: "leaf",
    selection: [],
    items: [
      {
        id: 1,
        name: "Root",
        children: [
          { id: 2, name: "Child 1" },
          { id: 3, name: "Child 2" },
          {
            id: 4,
            name: "Child 3",
            children: [
              { id: 5, name: "Grandchild 1" },
              { id: 6, name: "Grandchild 2" },
            ],
          },
        ],
      },
    ],
  }),
};
</script>
