<script>
import Service from './components/Service.vue';
import SearchBar from './components/SearchBar.vue';
import config from "../server_dashboard.json";
import qbit from "./assets/qbit_icon.png";

export default {
  components: {
    Service,
    SearchBar
  },
  data() {
    return {
      services: [
        { name: "Torrent client", ip: config.torrent, icon: qbit },
        { name: "Last fm scrobbler", ip: config.lfm, icon: "./src/assets/lastfm_icon.png" },
        { name: "Jellyfin", ip: config.jellyfin, icon: "./src/assets/jellyfin_icon.png" },
        { name: "Plex", ip: config.plex, icon: "./src/assets/plex_icon.png" },
        { name: "Pihole", ip: config.pihole, icon: "./src/assets/pihole_icon.png" },
        { name: "Sonarr", ip: config.base + config.sonarr, icon: "./src/assets/sonarr_icon.png" },
        { name: "Radarr", ip: config.base + config.radarr, icon: "./src/assets/radarr_icon.png" },
        { name: "Bazarr", ip: config.base + config.bazarr, icon: "./src/assets/bazarr_icon.png" },
        { name: "Prowlarr", ip: config.base + config.prowlarr, icon: "./src/assets/prowlarr_icon.png" },

      ]
    }
  }
}
</script>

<template>
  <header>
    <div class="searchbar">
      <SearchBar />
    </div>
    <div class="dashboard-container">
      <div class="dashboard">
        <div>
          <ul class="horizontal-list"> <!-- Add the ul tag here -->
            <li v-for="service in this.services" class="the_list">
              <Service :ip="service.ip" :name="service.name" :icon="service.icon" />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>

<style scoped>
.dashboard-container {
  display: flex;
  justify-content: flex;
  margin: 10vh 28vw 0 2vw;
  /* background-color: var(--clr-div); */
  padding: 2vh 15vh 15vh 15vh;
  border-radius: 1%;
  flex-wrap: wrap;
  /* border: solid 1px var(--clr-div-border); */
}

.searchbar {
  margin: 10vh 0vw 0vh 28vw;
}

.horizontal-list {
  padding: 0;
  margin-left: 3vw;
  display: flex;
  list-style: none;
  flex-wrap: wrap;
  /* Remove default list styles */
}

.the_list {
  padding: 0;
  /* Remove default padding */
  margin: 3vh 5vw 3vh 5vw;
  /* Remove default margin */
}
</style>
