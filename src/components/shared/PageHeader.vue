<template>
  <header class="top-navbar">
    <div class="sidebar-toggle clickable" id="menu-toggle">
      <i class="material-icons md-18">menu</i>
    </div>
    <div class="cluster-status">
      <i class="material-icons md-18">check_circle</i>
      {{ $t("page_header.cluster-status.details") }}
    </div>
    <div class="dropdown user-details clickable">
      <div class="dropdown-toggle" data-toggle="dropdown">
        <i class="material-icons md-18">account_circle</i>
        Hacluste
      </div>
      <ul class="dropdown-menu dropdown-menu-right">
        <li><a>Account Setting</a></li>
        <li><a>Help</a></li>
        <li><a>Logout</a></li>
      </ul>
    </div>
  </header>
</template>

<script>

export default {
  methods: {
    toggleMenu: function () {
      $('#sidebar-wrapper li').tooltip()
      $('#menu-toggle').click(function (e) {
        e.preventDefault()
        $('#wrapper').toggleClass('toggled')
        toggleTooltip()
      })
      function toggleTooltip () {
        // if the menu is not collapsed (meaning, it is open) we dont need to show the tooltips
        if ($('.main-menu').width() === 54) {
          $('#sidebar-wrapper li').tooltip()
        } else {
          $('#sidebar-wrapper li').tooltip('destroy')
        }
      }
    }
  },
  mounted: function () {
    this.toggleMenu()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

</style>
