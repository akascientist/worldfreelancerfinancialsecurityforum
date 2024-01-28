<template>
    <div class="row">
      <!-- Nav tabs -->
      <ul class="nav nav-tabs" id="navId">
        <li class="nav-item" v-for="(tab, index) in tabs" :key="index">
          <a :href="'#' + tab.id" class="nav-link" :class="{ active: tab.id === activeTab }" @click.prevent="showTab(tab.id)">{{ tab.name }}</a>
        </li>
      </ul>
  
      <!-- Tab panes -->
      <div class="tab-content">
        <div v-for="(tab, index) in tabs" :key="index" class="tab-pane fade" :class="{ 'show active': tab.id === activeTab }" :id="tab.id" role="tabpanel"></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        tabs: [
          { id: 'tab1Id', name: 'Active' },
          { id: 'tab2Id', name: 'Action' },
          { id: 'tab3Id', name: 'Another action' },
          { id: 'tab4Id', name: 'Action' },
          { id: 'tab5Id', name: 'Another link' }
        ],
        activeTab: 'tab1Id'
      };
    },
    methods: {
      showTab(tabId) {
        this.activeTab = tabId;
      }
    }
  }
  </script>
   