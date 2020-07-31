<template>
  <div>
    <section class="hero is-info is-small is-bold">
      <div class="hero-head">
        <div class="container">
          <b-navbar>
            <template
              slot="brand"
              class="container"
            >
              <b-navbar-item
                tag="router-link"
                :to="{ path: '/' }"
              >
                <img
                  src="../assets/optimity_logotype.png"
                  alt="Lightweight UI components for Vue.js based on Bulma"
                  style="min-height: 40px"
                >
              </b-navbar-item>
            </template>
            <template slot="end">
              <b-navbar-item tag="div">
                <div class="buttons">
                  <a class="button is-info is-inverted">
                    <strong>Customer Portal</strong>
                  </a>
                </div>
              </b-navbar-item>
            </template>
          </b-navbar>
        </div>
      </div>

      <div class="hero-body">
        <div class="container has-text-centered">
          <p class="title has-text-weight-light is-size-2 pb-5">
            Learn how to
            <vue-typer
              :text="[&quot;connect to your office VPN&quot;,&quot;secure a home network&quot;,&quot;troubleshoot WiFi connectivity&quot;,&quot;install a firewall&quot;,&quot;setup your virtual office&quot;]"
              :repeat="Infinity"
              :shuffle="false"
              initial-action="typing"
              :pre-type-delay="70"
              :type-delay="70"
              :pre-erase-delay="3500"
              :erase-delay="250"
              erase-style="clear"
              :erase-on-complete="false"
              caret-animation="blink"
            />
          </p>
          <p class="subtitle mb-3">
            With Optimity's Knowledge Base
          </p>
        </div>
      </div>
    </section>

    <section class="main-content columns">
      <div class="column is-10 is-offset-1">
        <section class="columns">
          <aside class="column is-2 section">
            <b-menu>
              <b-menu-list label="Collections">
                <b-menu-item
                  v-for="(item, i) of items"
                  :key="i"
                  :label="item.title"
                  :to="item.to"
                  tag="nuxt-link"
                  :icon="item.icon"
                  exact-active-class="is-active is-info"
                />
              </b-menu-list>
            </b-menu>
          </aside>

          <div class="container column">
            <nuxt />
          </div>
        </section>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'All',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' }
        }
      ]
    }
  }
}
</script>
<style>
/* .vue-typer {
  font-family: monospace;
} */

.vue-typer .custom.char {
  color: white;
  background-color: rgba(255, 255, 255, 0.2);
}
.vue-typer .custom.char.selected {
  background-color: #264f78;
}

.vue-typer .custom.caret {
  width: 2px;
  background-color: white;
}
</style>
