<template>
    <nav class="navbar is-dark">
      <div class="container">
        <div class="navbar-brand">
          <a class="navbar-item" href="../">
              <img src="static/wave.png" alt="Logo">
          </a>
          <span @click="display = !display" :class="['navbar-burger burger', {'is-active' : display }]" data-target="navbarMenu">
              <span></span>
              <span></span>
              <span></span>
          </span>
        </div>
        <div :class="['navbar-menu',{'is-active Navbar-menu': display}]" id="navbarMenu">
          <div class="navbar-end">
            <span class="navbar-item" v-for="(item, key) in navbar" :key="key">
              <router-link v-if="key <= 4" class="navbar-item button is-white is-outlined" :to="{path:item.router}">
                  <span class="icon">
                      <font-awesome-icon v-if="key == 7" :icon="['fab', item.icon]" />
                      <font-awesome-icon v-else :icon="['fas', item.icon]" />
                  </span>
                  <span v-text="item.name"></span>
              </router-link>
              <a v-if="key > 4"  class="navbar-item button is-white is-outlined" :href="item.link">
                <span class="icon">
                    <font-awesome-icon v-if="key == 7" :icon="['fab', item.icon]" />
                    <font-awesome-icon v-else :icon="['fas', item.icon]" />
                </span>
                <span v-text="item.name"></span>
              </a>
            </span>
          </div>
        </div>
      </div>
    </nav>
</template>
<script>
export default {
  name: '',
  data: () => ({
    navbar: [
      {name: '0', origin: 'Home', router: '/', icon: 'home'},
      {name: '1', origin: 'Projects', router: '/projects', icon: 'project-diagram'},
      {name: '2', origin: 'About', router: '/about', icon: 'info'},
      {name: '3', origin: 'Skills', router: '/skills', icon: 'star'},
      {name: '4', origin: 'DataBase', router: '/database', icon: 'project-diagram'},
      {name: '5', origin: 'Resume', link: 'https://drive.google.com/file/d/1WJG6qCVdnLnF2eu-s02A4Cd3hto6Fp92/view?usp=sharing', icon: 'file-alt'},
      {name: '6', origin: 'Contacts', link: 'https://github.com/Minaparnian', icon: 'envelope'},
      {name: '7', origin: 'Github', link: 'https://github.com/Minaparnian', icon: 'github-alt'}

    ],
    display: false
  })
}
</script>

<style>

.hero.is-info .navbar-menu {
  background-color: transparent;
}

.navbar-burger {
  color: #fff;
}

.Navbar-menu {
  height: 100%;
  width: 250px;
  position: fixed;
  z-index: -1;
  top: 0;
  right: 0;
  overflow-x: hidden;
  transition: 0.5s;
  padding: 0;
  padding-top: 50px;
}

</style>
