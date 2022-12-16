<template>
  <div class="dash bg-blue-900">
    <SideBar />

    <div>
      <div class="grid grid-cols-2 gap-4">
        <div class="grid-component grid grid-rows-2 grid-flow-col mr-4 bg-white rounded">
          <div class="text-gray-800 row-span-2 p-5 desc">
            <h2 class="mb-4">Mission Stats:</h2>
            <p>
              NASA's Volatiles Investigating Polar Exploration Rover, or VIPER, is a mobile robot that will go to the South Pole of the Moon to get a close-up view of the location.
            </p>
            <ul class="list-disc">
              <li>
                <h4>Position:</h4>
                <p>Dark side of the moon</p>
              </li>
            </ul>
          </div>
          <img class="row-span-2 rounded stats" src="http://www.nasa.gov/sites/default/files/thumbnails/image/viper_drilling_on_moon_copy.jpg" alt="viper" />
        </div>
        <div class="grid-component rounded">
          <img class="rounded" src="https://moon.nasa.gov/system/downloadable_items/99_s2-1280.jpg" alt="moon image" />
        </div>
        <div class="grid-component rounded text-center bg-white">
          <h3 class="text-gray-800 p-5 text-xl">Upcoming Tasks:</h3>
          <div v-for="task in tasks" :key="task.id" class="p-6">
            <div class="card text-white text-start rounded overflow-hidden shadow-md bg-blue-500">
              <div class="px-6 pt-4 pb-2">
                <div class="font-semibold text-md mb-2">
                  {{ task.taskName }}
                </div>
              </div>

              <div class="px-6 pb-2">
                <span class="inline-block text-white bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold mr-2 mb-2" :class="{'bg-red-400': task.weight === 1, 'bg-orange-400': task.weight > 0.5 && task.weight < 1, 'bg-yellow-400': task.weight === 0.5, 'bg-green-400': task.weight < 0.5}">
                  Importance: {{ task.weight }}
                </span>
              </div>
            </div>
          </div>
        </div>
        <div class="grid-component rounded text-center bg-white">
          <h3 class="text-gray-800 p-5 text-xl">LUNANET</h3>
          <img src="https://www.nasa.gov/sites/default/files/thumbnails/image/lunanet.png" alt="LUNANET" />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from '@/components/SideBar.vue';
import { Task } from '@/typings';
import CardVue from '@/components/Card.vue';

let tasks: Task[] = [
  {
    id: '1',
    taskName: 'Checking spacesuit',
    weight: 1,
    listName: 'Doinf'
  },
  {
    id: '2',
    taskName: 'Checking LTV',
    weight: 0.8,
    listName: 'To Do'
  },
]


export default defineComponent({
  name: 'DashboardView',
  components: {
    SideBar,
    Card: CardVue
  },
  data() {
    return {
      tasks
    }
  }
});
</script>

<style lang="scss" scoped>
.dash {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: left;
  padding: 1rem;
  overflow-x: scroll;
  height: 100vh;
  width: 100vw;
}

.grid-component {
  width: 100%;
  height: 100%;
}

.stats {
  height: 100%;
  min-width: 200px;
}
</style>