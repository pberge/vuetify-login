<template>
  <v-app
    dark
    id="inspire"
  >
    <v-toolbar>
      <div class="flex-grow-1"></div>
      <v-btn text small href="https://www.vmware.com/worldwide.html">
        <v-icon left>fa-globe-europe</v-icon> US
      </v-btn>
      <v-menu offset-y open-on-hover>
        <template v-slot:activator="{ on }">
          <v-btn text small v-on="on">
            Login <v-icon right>fa-chevron-down</v-icon>
          </v-btn>
        </template>
        <v-list>
          <v-list-item>
            <v-btn text href="">My VMware</v-btn>
          </v-list-item>
          <v-list-item>
             <v-btn text href="">Partner Central</v-btn>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn text small href="https://www.vmware.com/training.html">Training</v-btn>
      <v-btn text small href="https://communities.vmware.com/welcome">Community</v-btn>
      <v-btn text small href="https://www.vmware.com/vmwarestore/">Store</v-btn>
      <v-btn text small onclick="window.location='tel:+18774869273';">
        <v-icon left>fa-phone-alt</v-icon> 1-877-486-9273
      </v-btn>
      <v-text-field
        label="Search"
        solo
      >
        <v-btn text small action="http://www.vmware.com/search.html"><v-icon right>fa-search</v-icon></v-btn>
      </v-text-field>
     

      <!-- <div class="flex-grow-1"></div> -->
    </v-toolbar>

    <v-navigation-drawer
      v-model="drawer"
      permanent
    >
      <v-list-item>
        <v-list-item-title>VMWARE</v-list-item-title>
      </v-list-item>
      <v-list >
        <v-list-item
          v-for="item in items"
          :key="item.text"
          link
        >
          <router-link :to="item.link">
            <v-list-item-content>
              <v-icon>{{item.icon}}</v-icon>
              <v-list-item-title>{{ item.text }}</v-list-item-title>
            </v-list-item-content>
          </router-link>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: null,
      items: [
        { icon: 'fa-cloud', text: 'VMWARE CLOUD', link: '' },
        { icon: 'fa-boxes', text: 'PRODUCTS', link: '' },
        { icon: 'fa-cogs', text: 'SUPPORT', link: '' },
        { icon: 'fa-cogs', text: 'SOLUTIONS', link: '' },
        { icon: 'fa-briefcase', text: 'PROFESSIONAL SERVICES', link: '' },
        { icon: 'fa-save', text: 'DOWNLOADS', link: '' },
        { icon: 'fa-users', text: 'PARTNER PROGRAMS', link: '' },
        { icon: 'fa-building', text: 'COMPANY', link: '' }
      ],
    }),
    props: {
      source: String
    }
  }
</script>

<style scoped>
  .v-navigation-drawer {
    width: 135px !important;
  }

  .input-group__details:after {
    background-color: rgba(255, 255, 255, 0.32) !important;
  }

  .v-list-item {
    justify-content: center;
  }

  .v-list-item__title {
    text-align: center;
    color: white;
    font-size: 0.7em;
    margin-top: 0.3em;
    white-space: nowrap;
    overflow: hidden;
    white-space: initial;
  }

  .v-navigation-drawer {
    background: #464547 none repeat scroll 0 0 !important;  
  }

  .v-toolbar {
    background-color: #717074 !important;
    background: transparent;
    position: fixed;
    left: 135px;
    right: 0;
  }

  a {
    text-decoration: none;
    width: 100%;
  }

  .v-icon {
    color: white !important;
  }

  .v-btn {
    width: auto !important;
    color: white !important;
    font-weight: normal;
    font-size: 0.7em !important;
    text-transform: capitalize;
  }

  .v-btn .v-icon {
    font-size: 1.5em;
  }

  .v-menu__content {
    background: #464547 !important;
  }

  .v-list {
    background: #464547 !important;
  }

  
</style>
