<script setup lang="ts">
  const api_key = "7ac410f664a527a56d39f7d9adb08ca4"
  const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=london&appid=7ac410f664a527a56d39f7d9adb08ca4`;

``
</script>
<template> 
  <body>
    <div class="  hero min-h-screen bg-accent">
      <div class="hero-content text-center ">
          <div class="max-w-md ">
              <h1 class="text-5xl font-bold">London 31.12°</h1>
              <div class="flex justify-center">

              </div>
              <div class="flex justify-center">
                  <div class="form-control ">
                      <div class="input-group pt-3">
                          <input type="text" placeholder="Search…" class="input input-bordered"  />
                          <button class="btn btn-square " >
                              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24"
                                  stroke="currentColor">
                                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                      d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                              </svg>
                          </button>
                      </div>
                  </div>
              </div>

          </div>
      </div>
  </div>
  </body>  
</template>

<style scoped>
  body{
    height: 100vh;
  }

</style>