<template>
  <div>
    <navbar />
    <sidebar  :sidebars="sidebars"/>
   <div class="main-content">
      <section class="section">
        <!-- <title-stisla /> -->
        <nuxt />         
        <div class="section-body" />
      </section>
    </div>

  </div>
  
</template>

<script>
export default {
  data (){
    return {
     sidebars: [
        {
          name: 'Dashboard',
          link: '/',
          icon: 'fas fa-tachometer-alt'
        },
        {
          name: 'Increment',
          link: '/increment',
          icon: 'fas fa-fire'
        },
        {
          name: 'users',
          link: '/users',
          icon: 'fas fa-users'
        },
        {
          name: 'Books',
          link: '/books',
          icon: 'fas fa-book'
        },{
          name: 'Reader',
          link: '/reader',
          icon: 'fas fa-book-reader'
        }
      ]
    }
  }
}
</script>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
