<template>
    <div class="navbar bg-base-100">
        <a class="btn btn-ghost normal-case text-xl"><router-link to="/">Home</router-link></a>
        <router-link to="/login">Login</router-link>
      </div>
      <slot/>
</template>