<template>
  <v-container>
      <v-select
        v-model="select"
        :hint="`${select.state}, ${select.abbr}`"
        :items="items"
        item-title="state"
        item-value="abbr"
        label="Select"
        persistent-hint
        return-object
        single-line
      ></v-select>
  </v-container>
</template>

<script>
  export default {
    data: () => ({
      select: { state: 'Florida', abbr: 'FL' },
      items: [
        { state: 'Florida', abbr: 'FL' },
        { state: 'Georgia', abbr: 'GA' },
        { state: 'Nebraska', abbr: 'NE' },
        { state: 'California', abbr: 'CA' },
        { state: 'New York', abbr: 'NY' },
      ],
    }),
  }
</script>
