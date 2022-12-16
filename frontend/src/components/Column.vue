<template>
  <div class="column rounded justify-content-center mr-4 bg-blue-500">
    <header class="mb-4 p-4 pb-0">
      <h1 class="font-semibold text-md mb-1 text-white">{{ title }}</h1>
    </header>

    <div
      class="card-holder p-4 pt-0"
      @dragover.prevent
      @dragenter.prevent
    >
      <div v-for="task in sorted_tasks" :key="task.id" class="pb-6">
        <Card
          :task-name="task.taskName"
          :weight="task.weight"
          draggable
        />
      </div>

      <div class="flex flex-row" v-on:click="toggleInput">
        <div v-if="!showInput" class="flex flew-row cursor-pointer">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">
            <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5v15m7.5-7.5h-15" />
          </svg>

          <p class="pl-2">Add a new task</p>
        </div>

        <div v-if="showInput">
          <div class="card max-w-sm rounded overflow-hidden shadow-md bg-white">
            <form class="px-6 pt-4 pb-2" @submit.prevent="addTask({id, taskName, weight, listName: title})">
              <div class="text-md mb-2">
                <input class="pb-2" type="text" name="taskName" placeholder="Enter a new task" v-model="taskName" required />
                <input class="pb-2" type="number" name="weight" placeholder="Enter task importance (0 -> 1)" v-model="weight" required />
              </div>
            </form>
          </div>

          <div class="flex flex-row align-bottom">
            <button class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-2" @click="addTask({id, taskName, weight, listName: title})">
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
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CardVue from './Card.vue';
import { Task } from '../typings'

let tasks: Task[] = [
  {
    id: '1',
    taskName: 'Garbage collector',
    weight: 1,
    listName: 'Done'
  },
  {
    id: '2',
    taskName: 'Collect samples',
    weight: 0.1,
    listName: 'Done'
  },
  {
    id: '3',
    taskName: 'Rest',
    weight: 0.4,
    listName: 'Done'
  },
  {
    id: '4',
    taskName: 'Study and do research',
    weight: 0.3,
    listName: 'Done'
  },
  {
    id: '5',
    taskName: 'Study and do research',
    weight: 0.5,
    listName: 'Doing'
  },
  {
    id: '6',
    taskName: 'Maintenance',
    weight: 0.7,
    listName: 'Doing'
  },
  {
    id: '7',
    taskName: 'Remote control rover',
    weight: 1,
    listName: 'To Do'
  },
  {
    id: '8',
    taskName: 'Stretching',
    weight: 0.1,
    listName: 'Doing'
  },
  {
    id: '9',
    taskName: 'Groud control meeting',
    weight: 0.4,
    listName: 'To Do'
  },
  {
    id: '10',
    taskName: 'Explore surroundings',
    weight: 0.3,
    listName: 'Doing'
  },
]

let weight: number

export default defineComponent({
  name: 'ColumnComponent',
  components: {
    Card: CardVue
},
  props: {
    title: {
      type: String,
      required: true,
      default: 'To Do'
    }
  },
  data() {
    return {
      tasks,
      showInput: false,
      id: '5',
      taskName: '',
      weight
    }
  },
  methods: {
    addTask(task: Task) {
      this.tasks.push(task)
      this.id += 1
      this.taskName = ''
      this.showInput = false
      console.log(this.showInput)
    },
    toggleInput() {
      this.showInput = true
    },
    cancel() {
      this.showInput = false
    }
  },
  computed: {
    sorted_tasks() {
      tasks.filter((task) => task.listName.toLowerCase() === this.title.toLowerCase())
      return this.tasks.sort((a, b) => {
        if(a.weight > b.weight) return -1;
        if(a.weight < b.weight) return 1;
        return 0;
      })
    }
  }
});
</script>

<style lang="scss" scoped>
.column {
  display: flex;
  flex-direction: column;
  min-width: 320px;
  max-height: 95vh;
}

.card-holder {
  overflow-y: scroll;
}

.card {
  max-width: 288px;
}
</style>