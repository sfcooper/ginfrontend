<template>
  <header class="header">
    <nuxt-link to="/" class="logo">The Gin Detective</nuxt-link>
        <input id="menu-btn" class="menu-btn" type="checkbox" />
        <label class="menu-icon" for="menu-btn"><span class="navicon" /></label>
        <ul class="menu">
            <li><nuxt-link to="/gins">Gins</nuxt-link></li>
            <li><nuxt-link to="/distilleries">Distileries</nuxt-link></li>
        </ul>
  </header>
</template>
