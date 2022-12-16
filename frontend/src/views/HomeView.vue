<template>
  <div class="home bg-blue-900">
    <SideBar />

    <div v-for="column in columns" :key="column.id">
      <Column :title="column.title" />
    </div>

    <div>
      <div v-on:click="toggleInput" class="card max-w-sm rounded overflow-hidden shadow-md bg-white">
        <form class="px-6 pt-4 pb-2" @submit.prevent="addColumn(title)">
          <div class="text-md mb-2">
            <input class="pb-2" type="text" name="taskName" placeholder="Enter a new column" v-model="title" required />
          </div>
        </form>
      </div>

      <div v-if="showInput" class="flex flex-row align-bottom">
        <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-2 button" @click="addColumn(title)">
          Add Card
        </button>

        <button class="ml-4 bg-red-500 hover:bg-red-600 text-white py-2 px-2 rounded mt-2" @click="cancel">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ColumnVue from '@/components/Column.vue';
import SideBar from '@/components/SideBar.vue';

let columns = [
  {
    id: '1',
    title: 'To Do'
  },
  {
    id: '2',
    title: 'Doing'
  },
  {
    id: '3',
    title: 'Done'
  }
]

let id = '4'

export default defineComponent({
  name: 'HomeView',
  components: {
    Column: ColumnVue,
    SideBar
  },
  data() {
    return {
      title: '',
      columns,
      showInput: false
    }
  },
  methods: {
    addColumn(title: string) {
      id += '1'
      this.columns.push({id, title})
      this.title = ''
      this.showInput = false
    },
    toggleInput() {
      this.showInput = true
    },
    cancel() {
      this.showInput = false
    }
  }
});
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: left;
  padding: 1rem;
  overflow-x: scroll;
  height: 100vh;
}

.button {
  max-width: fit-content;
}
</style>