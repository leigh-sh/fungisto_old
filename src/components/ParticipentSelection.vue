<template>
  <v-layout column justify-space-between class="main-wrapper">
    <v-flex shrink>
      <h1>Employees</h1>
    </v-flex>
    <v-flex>
      <ul>
        <li v-for="(person, index) in persons" :key="index">
          <v-layout align-center justify-space-between>
            <v-flex shrink>
              {{ person.name }}
            </v-flex>
            <v-flex shrink>
              <v-switch @change="selectParticipent(person)"></v-switch>
            </v-flex>
          </v-layout>
        </li>
      </ul>
    </v-flex>
    <v-flex shrink>
      <v-layout justify-space-between>
        <v-flex shrink>
          <v-btn>Raffle</v-btn>
        </v-flex>
        <v-flex shrink>
          <v-btn @click="$emit('routeChange', 'start')">
            Back
            <v-icon>mdi-chevron-right</v-icon>
          </v-btn>
        </v-flex>
      </v-layout>
    </v-flex>

  </v-layout>
</template>

<script>
export default {
  data: () => {
    return {
      persons: [
        { name: 'moshe', isSelected: false },
        { name: 'haim', isSelected: false },
        { name: 'yosi', isSelected: false },
        { name: 'david', isSelected: false },
        { name: 'avi', isSelected: false }
      ]
    }
  },
  methods: {
    selectParticipent(person) {
      this.persons.forEach( (dataPerson) => {
        if (person.name === dataPerson.name) {
          dataPerson.isSelected = !dataPerson.isSelected
        }
      })
      // console.log(`${person.name} is ${person.isSelected ? 'selected' : 'unselected' }`)
    }
  },
  computed: {
    selectedParticipents () {
      return this.persons.filter( person => {
        return person.isSelected
      })
    }
  }

}
</script>

<style scoped lang="stylus">
  ul
    padding: 0 !important
    list-style-type: none
</style>
