<template>
  <div class="sidebar" v-if="hasAnyAuthority('ROLE_ADMIN')">
    <b-sidebar
      bg-variant="dark"
      text-variant="light"
      id="sidebar-footer"
      data-cy="sidebar"
      no-close-on-route-change
      no-close-on-esc
      visible
    >
      <template v-slot:footer="{ hide }">
        <div class="d-flex text-light align-items-center">
          <b-button block variant="primary" @click="hide">
            <font-awesome-icon icon="angle-double-left" />
          </b-button>
        </div>
      </template>
      <div class="px-3">
        <b-nav vertical text-variant="light" aria-label="Sidebar" no-header>
          <b-nav-item to="/applications/instances">
            <font-awesome-icon icon="cube" />
            <span>Instances</span>
          </b-nav-item>
          <b-nav-item to="/applications/metric" data-cy="metricsMenu">
            <font-awesome-icon icon="tachometer-alt" />
            <span>Metrics</span>
          </b-nav-item>
          <b-nav-item to="/applications/caches" data-cy="caches-menu">
            <font-awesome-icon icon="layer-group" />
            <span>Caches</span>
          </b-nav-item>
          <b-nav-item to="/applications/health" data-cy="healthMenu">
            <font-awesome-icon icon="heart" />
            <span>Health</span>
          </b-nav-item>
          <b-nav-item to="/applications/configuration" data-cy="configurationMenu">
            <font-awesome-icon icon="list" />
            <span>Configuration</span>
          </b-nav-item>
          <b-nav-item to="/applications/loggers" data-cy="logsMenu">
            <font-awesome-icon icon="tasks" />
            <span>Logs</span>
          </b-nav-item>
          <b-nav-item to="/applications/logfile" data-cy="logsfileMenu">
            <font-awesome-icon icon="indent" />
            <span>Logfile</span>
          </b-nav-item>
          <b-nav-item v-if="openAPIEnabled" to="/applications/docs" data-cy="openAPIMenu">
            <font-awesome-icon icon="book" />
            <span>API</span>
          </b-nav-item>
        </b-nav>
        <span class="fixed-bottom hipster img-fluid"></span>
      </div>
    </b-sidebar>
  </div>
</template>

<script lang="ts" src="./jhi-sidebar.component.ts"></script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@media screen and (max-width: 1150px) {
  span {
    display: none;
  }
  .hipster {
    max-height: 100px !important;
  }
}

@media screen and (min-height: 500px) and (max-height: 600px) {
  .hipster {
    max-height: 100px !important;
  }
}

@media screen and (max-height: 500px) {
  .hipster {
    display: none !important;
  }
}

.btn-block {
  border-radius: 0;
}
</style>
