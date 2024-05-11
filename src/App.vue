<template>
  <heafer class="header-container">
    <a href="#">
      <img src="./assets/logo.png" alt="Logo">
    </a>
    <a href="#">
      <div class="header-status-container">
        Day complete
        <CheckCircleIcon class="icon-complete" />
      </div>

      <div class="header-status-container">
        <div>Progress: <span>50%</span></div>
        <div class="circle-progress"></div>
      </div>
    </a>
  </heafer>
  <main class="main-container">
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Et dolorum nam suscipit, quam voluptates consequatur
    dignissimos deserunt blanditiis modi pariatur eum, sint sed! Nostrum laudantium voluptas ab exercitationem
    voluptatibus quisquam ut earum tempora provident? Aliquam doloremque officiis odit provident exercitationem,
    veritatis nostrum labore ab dicta ullam nulla eaque numquam tempore eius!
  </main>
  <nav class="nav-container">
    <ul>
      <li v-for="icon, page in navItems" :key="page">
        <a :href="`#${page}`" class="nav-link">
          <component :is="icon" class="nav-icon" />{{ page }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup>
import { CheckCircleIcon } from "@heroicons/vue/24/solid";
import { ClockIcon, ListBulletIcon, ChartBarIcon } from "@heroicons/vue/24/outline";

const navItems = {
  timeline: ClockIcon,
  activities: ListBulletIcon,
  progress: ChartBarIcon
};

</script>

<style lang="scss" scoped>
* {
  all: initial;
}

.header-container {
  position: sticky;
  top: 0;
  z-index: 20;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #ccc;
  background: #ffffff;
  padding: 3px;
}

.header-status-container {
  display: flex;
  align-items: center;
  gap: 1px;
  font-size: 1em;

  .icon-complete {
    height: 1.5em;
    color: green;
  }

  .circle-progress {
    width: 1.2em;
    height: 1.2em;
    background-color: orange;
    border-radius: 50%;
  }
}

.main-container {
  display: flex;
  flex-grow: 1;
  flex-direction: column;
}

.nav-container {
  position: sticky;
  bottom: 0;
  z-index: 10;
  background-color: #ffffff;
  border-top: 1px solid #ccc;
  padding: 4px;

  ul {
    display: flex;
    align-items: center;
    justify-content: space-around;


    li {
      flex: 1;
    }
  }

  .nav-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 2px;
    font-size: medium;
  }

  .nav-icon {
    height: 1.5em;
    width: 1.5em;
  }
}
</style>