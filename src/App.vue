<script>
import Service from './components/Service.vue';
import config from "../server_dashboard.json";

export default {
  components: {
    Service
  },
  data() {
    return {
      services: [
        { name: "Torrent client", ip: config.torrent },
        { name: "Last fm scrobbler", ip: config.lfm },
        { name: "Jellyfin", ip: config.jellyfin },
        { name: "Plex", ip: config.plex },
        { name: "Pihole", ip: config.pihole },
        { name: "Sonarr", ip: config.base + config.sonarr },
        { name: "Radarr", ip: config.base + config.radarr },
        { name: "Bazarr", ip: config.base + config.bazarr },
        { name: "Prowlarr", ip: config.base + config.prowlarr },

      ]
    }
  }
}
</script>

<template>
  <header>
    <li v-for="service in this.services">
      <Service :ip="service.ip" :name="service.name" />
    </li>
  </header>
</template>

<style scoped></style>
