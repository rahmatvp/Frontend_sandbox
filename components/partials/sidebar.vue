<template>
  <div>
       <div class="main-sidebar">
        <aside id="sidebar-wrapper">
          <div class="sidebar-brand">
            <a href="index.html">My Admin</a>
          </div>
          <div class="sidebar-brand sidebar-brand-sm">
            <a href="index.html">MA</a>
          </div>
          <ul class="sidebar-menu">
              <!-- <li><a class="nav-link" href="credits.html"><i class="fas fa-pencil-ruler"></i> <span>Credits</span></a></li> -->
         
          <li v-for="(sidebar,i) in sidebars" :key="i">
            <nuxt-link class="nav-link" :to="sidebar.link">
              <i :class="sidebar.icon" />
              <span>{{ sidebar.name }} </span>
            </nuxt-link>
          </li>
          
          </ul>

            <!-- <div class="mt-4 mb-4 p-3 hide-sidebar-mini">
              <a href="https://getstisla.com/docs" class="btn btn-primary btn-lg btn-block btn-icon-split">
                <i class="fas fa-rocket"></i> Documentation
              </a>
            </div> -->
        </aside>
      </div>
  </div>
</template>

<script>
export default {
  props: {
    sidebars: {
      type: Array,
      default: () => []
    }

  }
}
</script>
