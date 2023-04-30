<script setup>
import { peopleHeader } from './people.config'

const { fetchPeople } = usePeopleLoader

const selecetedPersonId = ref('')
const searchTerm = ref('')
const currentPage = ref('')

const people = fetchPeople(currentPage, searchTerm)
</script>

<template>
  <SearchTerm v-model="searchTerm" />
  <DataTable :headers="peopleHeader" :data="people" />
  <Pagination v-model="currentPage" />
  <PlanetModal :selectedPersonId="selecetedPersonId" />
</template>
