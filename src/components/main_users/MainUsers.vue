<template>
  <li class="nav-item nav-profile dropdown mr-0 mr-sm-2">
    <a class="nav-link dropdown-toggle" href="#" data-toggle="dropdown" id="profileDropdown">
      <img src="https://via.placeholder.com/40x40" alt="profile"/>
      <span class="nav-profile-name">{{ text }}</span>
    </a>
    <div class="dropdown-menu dropdown-menu-right navbar-dropdown" aria-labelledby="profileDropdown">
      <MainUserOptions />
    </div>
  </li>
</template>

<script>
import MainUserOptions from './MainUserOptions'

export default {
    name: "MainUsers",
    components: {
        MainUserOptions
    },
    props: {
        text: String
    },
}
</script>