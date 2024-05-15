<script>
import prowlarr from "./assets/prowlarr_icon.png";
import bazarr from "./assets/bazarr_icon.png";
import radarr from "./assets/radarr_icon.png";
import sonarr from "./assets/sonarr_icon.png";
import pihole from "./assets/pihole_icon.png";
import plex from "./assets/plex_icon.png";
import Service from './components/Service.vue';
import SearchBar from './components/SearchBar.vue';
import config from "../server_dashboard.json";
import qbit from "./assets/qbit_icon.png";
import lfm from "./assets/lastfm_icon.png";
import jellyfin from "./assets/jellyfin_icon.png";

export default {
  components: {
    Service,
    SearchBar
  },
  data() {
    return {
      services1: [
        { name: "Torrent client", ip: config.torrent, icon: qbit },
        { name: "Last fm scrobbler", ip: config.lfm, icon: lfm },
        { name: "Jellyfin", ip: config.jellyfin, icon: jellyfin },
      ],
      services2: [
        { name: "Plex", ip: config.plex, icon: plex },
        { name: "Pihole", ip: config.pihole, icon: pihole },
        { name: "Sonarr", ip: config.base + config.sonarr, icon: sonarr },

      ],
      services3: [
        { name: "Radarr", ip: config.base + config.radarr, icon: radarr },
        { name: "Bazarr", ip: config.base + config.bazarr, icon: bazarr },
        { name: "Prowlarr", ip: config.base + config.prowlarr, icon: prowlarr },

      ]
    }
  }
}
</script>

<template>
  <div class="searchbar">
    <SearchBar />
  </div>
  <div class="dashboard-container">
    <template v-for="service in this.services1">
      <Service :ip="service.ip" :name="service.name" :icon="service.icon" class="item" />
    </template>
  </div>
  <div class="dashboard-container2">
    <template v-for="service in this.services2">
      <Service :ip="service.ip" :name="service.name" :icon="service.icon" class="item" />
    </template>
  </div>
  <div class="dashboard-container3">
    <template v-for="service in this.services3">
      <Service :ip="service.ip" :name="service.name" :icon="service.icon" class="item" />
    </template>
  </div>
</template>

<style scoped>
.dashboard-container {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  margin: 10vh 28vw 0 2vw;
  /* background-color: var(--clr-div); */
  border-radius: 1%;
  flex-wrap: wrap;
  /* width: 33%; */
  /* border: solid 1px var(--clr-div-border); */
}

.dashboard-container2 {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  margin: 5vh 28vw 0 2vw;
  /* background-color: var(--clr-div); */
  border-radius: 1%;
  flex-wrap: wrap;
  /* width: 33%; */
  /* border: solid 1px var(--clr-div-border); */
}

.dashboard-container3 {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
  margin: 5vh 28vw 0 2vw;
  /* background-color: var(--clr-div); */
  border-radius: 1%;
  flex-wrap: wrap;
  /* width: 33%; */
  /* border: solid 1px var(--clr-div-border); */
}

.searchbar {
  margin: 10vh 0vw 0vh 28vw;
}

.item {
  margin: 2dvh 2dvw 2dvh 2dvw;
}

@media screen and (max-width: 1100px) {
  .dashboard-container {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    margin: 10vh 2vw 0 2vw;
    /* background-color: var(--clr-div); */
    border-radius: 1%;
    flex-wrap: wrap;
    /* width: 33%; */
    /* border: solid 1px var(--clr-div-border); */
  }

  .dashboard-container2 {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    margin: 5vh 2vw 0 2vw;
    /* background-color: var(--clr-div); */
    border-radius: 1%;
    flex-wrap: wrap;
    /* width: 33%; */
    /* border: solid 1px var(--clr-div-border); */
  }

  .dashboard-container3 {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    margin: 5vh 2vw 0 2vw;
    /* background-color: var(--clr-div); */
    border-radius: 1%;
    flex-wrap: wrap;
    /* width: 33%; */
    /* border: solid 1px var(--clr-div-border); */
  }

  .item {
    margin: 2dvh 2dvw 2dvh 2dvw;
  }
}
</style>
