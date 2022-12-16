<template>
  <aside class="sidebar w-64 bg-blue-500 mr-4 rounded" aria-label="Sidebar">
    <div class="overflow-y-auto py-4 px-3">
      <a href="#" class="flex items-center pl-2.5 mb-5">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e5/NASA_logo.svg/2449px-NASA_logo.svg.png" class="mr-3 h-6sm:h-7" alt="nasa" style="max-width: 80px;" />
        <span class="self-center text-xl font-semibold whitespace-nowrap text-gray-100">NASA</span>
      </a>
      <ul class="space-y-2">
        <li>
          <router-link to="/" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg aria-hidden="true" class="w-6 h-6 text-gray-100 transition duration-75" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M2 10a8 8 0 018-8v8h8a8 8 0 11-16 0z"></path><path d="M12 2.252A8.014 8.014 0 0117.748 8H12V2.252z"></path></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Dashboard</span>
          </router-link>
        </li>
        <li>
          <router-link to="/tasks" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 12h16.5m-16.5 3.75h16.5M3.75 19.5h16.5M5.625 4.5h12.75a1.875 1.875 0 010 3.75H5.625a1.875 1.875 0 010-3.75z" /></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Tasks</span>
          </router-link>
        </li>
        <li>
          <a href="#" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M9.594 3.94c.09-.542.56-.94 1.11-.94h2.593c.55 0 1.02.398 1.11.94l.213 1.281c.063.374.313.686.645.87.074.04.147.083.22.127.324.196.72.257 1.075.124l1.217-.456a1.125 1.125 0 011.37.49l1.296 2.247a1.125 1.125 0 01-.26 1.431l-1.003.827c-.293.24-.438.613-.431.992a6.759 6.759 0 010 .255c-.007.378.138.75.43.99l1.005.828c.424.35.534.954.26 1.43l-1.298 2.247a1.125 1.125 0 01-1.369.491l-1.217-.456c-.355-.133-.75-.072-1.076.124a6.57 6.57 0 01-.22.128c-.331.183-.581.495-.644.869l-.213 1.28c-.09.543-.56.941-1.11.941h-2.594c-.55 0-1.02-.398-1.11-.94l-.213-1.281c-.062-.374-.312-.686-.644-.87a6.52 6.52 0 01-.22-.127c-.325-.196-.72-.257-1.076-.124l-1.217.456a1.125 1.125 0 01-1.369-.49l-1.297-2.247a1.125 1.125 0 01.26-1.431l1.004-.827c.292-.24.437-.613.43-.992a6.932 6.932 0 010-.255c.007-.378-.138-.75-.43-.99l-1.004-.828a1.125 1.125 0 01-.26-1.43l1.297-2.247a1.125 1.125 0 011.37-.491l1.216.456c.356.133.751.072 1.076-.124.072-.044.146-.087.22-.128.332-.183.582-.495.644-.869l.214-1.281z" /><path stroke-linecap="round" stroke-linejoin="round" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" /></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Settings</span>
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-100 transition duration-75" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10 9a3 3 0 100-6 3 3 0 000 6zm-7 9a7 7 0 1114 0H3z" clip-rule="evenodd"></path></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Users</span>
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-100 transition duration-75" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M3 3a1 1 0 00-1 1v12a1 1 0 102 0V4a1 1 0 00-1-1zm10.293 9.293a1 1 0 001.414 1.414l3-3a1 1 0 000-1.414l-3-3a1 1 0 10-1.414 1.414L14.586 9H7a1 1 0 100 2h7.586l-1.293 1.293z" clip-rule="evenodd"></path></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Sign In</span>
          </a>
        </li>
        <li>
          <a href="#" class="flex items-center p-2 text-base font-normal text-gray-100 rounded-lg hover:bg-blue-800">
            <svg aria-hidden="true" class="flex-shrink-0 w-6 h-6 text-gray-100 transition duration-75" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M5 4a3 3 0 00-3 3v6a3 3 0 003 3h10a3 3 0 003-3V7a3 3 0 00-3-3H5zm-1 9v-1h5v2H5a1 1 0 01-1-1zm7 1h4a1 1 0 001-1v-1h-5v2zm0-4h5V8h-5v2zM9 8H4v2h5V8z" clip-rule="evenodd"></path></svg>
            <span class="flex-1 ml-3 whitespace-nowrap">Sign Up</span>
          </a>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'SideBar'
});
</script>

<style lang="scss" scoped>
.sidebar {
  height: 95vh;
  min-width: 250px;
}
</style>