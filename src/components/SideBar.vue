<template>
    <q-drawer show-if-above side="left" behavior="desktop" :width="279" class="colorBackground">
      <!-- Profile Image -->
      <div class="flex flex-center column q-mt-lg q-mb-xs">
        <img :src="require('@/assets/Ellipse.png')" alt="Custom Image" class="profile-image" />
      </div>
      <!-- Sidebar Title -->
      <div class="flex flex-center text-bold text-settings">Kinetic</div>
      <!-- Sidebar Tree -->
      <q-list class="q-ml-xs">
        <q-tree :nodes="sidebarTreeData" node-key="label" :default-expand-all="false" selected-color="primary" v-model:selected="selectedKey" >
          <template v-slot:default="{ node, active }">
            <q-item :class="{ 'hovered': active }" hoverable>
              <!-- Icon Section -->
              <q-item-section>
                <q-icon :name="node.icon" size="40px" color="white" />
              </q-item-section>
              <!-- Label Section -->
              <q-item-section>
                <q-router-link :to="node.link" class="sidebar_parent_text">
                  {{ node.label }}
                </q-router-link>
              </q-item-section>
            </q-item>
          </template>
        </q-tree>
      </q-list>
    </q-drawer>
  </template>
  
  <script>
  import { ref } from "vue";
  
  export default {
    name: "SidebarList",
    setup() {
      const hoveredNode = ref(null);
      const selectedKey = ref(null);
  
      const sidebarTreeData = ref([
        {
          icon: "home",
          label: "Main page",
          link: "/",
        },
        {
          icon: "calendar_today",
          label: "Calendar",
          link: "/calendar",
          children: [
            { label: "Daily exercise", link: "/daily-exercise" },
            { label: "Competitions", link: "/competitions" },
            { label: "My results", link: "/my-results" },
          ],
        },
        {
          icon: "analytics",
          label: "Analytics",
          link: "/analytics",
        },
        {
          icon: "settings",
          label: "Settings",
          link: "/settings",
        },
      ]);
  
      return {
        sidebarTreeData,
        hoveredNode,
        selectedKey
      };
    },
  };
  </script>
  
  <style>
  /* Drawer Background */
  .colorBackground {
    background: #1d2146;
  }

  .q-tree__node-header-content {
    color: white !important;
  }
  
  /* Sidebar Title */
  .text-settings {
    color: white;
    font-family: "Montserrat Alternates";
    font-size: 16px;
  }
  
  /* Sidebar Text Styling */
  .sidebar_parent_text {
    color: white;
    font-family: "" !important;
    font-size: 16px;
    margin-left: 5px;
    transition: color 0.2s ease-in-out;
  }

  .q-tree__node-header-content {
    color: white;
    font-family: "Montserrat Alternates" !important;
    font-size: 16px;
    margin-left: 5px;
    transition: color 0.2s ease-in-out; /* Replace 'YourFontName' with your desired font */
}
    .q-tree__node-header {
        border-top-left-radius: 4px;
        border-top-right-radius: 4px;
        margin-right: 3px;
    }
  
  .hovered {
  background-color: rgba(0, 0, 0, 0.1) !important; /* Add a subtle background on hover */
}
  
  .q-icon.notranslate.material-icons.q-tree__arrow {
    color: white;
  }
  
  
  /* Image of Kinetics */
  .profile-image {
    width: 125px;
    height: 125px;
    border-radius: 50%;
  }
  </style>