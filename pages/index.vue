<script setup lang="ts">
``
const cookie = useCookie("city");
const search = ref(cookie.value);
const input = ref("");
if(! cookie.value){
    cookie.value = 'london'
        }
const { data: city, error } = useAsyncData("city", async () => {
    let response;
    try{
        
        response = await $fetch(`https://api.openweathermap.org/data/2.5/weather?q=${search.value}&units=metric&appid=${api_key}`
)
return response
    }catch(error){
        console.log(error);
        search.value = cookie.value
    }
    return response;
},{
    watch:[
        search
    ]});
const hendleSearch = () =>{
    search.value = input.value.trim().split(" ").join("+");
    cookie.value = search.value;
    input.value = "";
    console.log('clickes')
}
</script>
<template>
  
  <body class="bg-accent">
    <div class="  hero min-h-screen">
      <div class="hero-content text-center ">
          <div class="max-w-md ">
              <h1 class="text-5xl font-bold">{{city.name}} {{city.main.temp}}°</h1>
              <div class="flex justify-center">

              </div>
              <div class="flex justify-center">
                  <div class="form-control ">
                      <div class="input-group pt-3">
                          <input type="text" placeholder="Search…" class="input input-bordered"  v-model="input"/>
                          <button class="btn btn-square " @click="hendleSearch">
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