<template>
  <q-layout >
    <q-header elevated style="background-color:#4CC089">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />

        <q-toolbar-title>
          Proyecto
        </q-toolbar-title>

        <div>Fecha status</div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
      content-class="bg-grey-1"
    >
      <q-list>
        <q-item-label
          header
          class="text-grey-8"
        >
          Menú
        </q-item-label>
        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Proyecto',
    icon: 'school'
  },
  {
    title: 'Scrum Team',
    icon: 'code'
  },
  {
    title: 'Product Backlog',
    icon: 'chat'
  },
  {
    title: 'Tablero Kavan',
    icon: 'record_voice_over'
  },
  {
    title: 'Informes',
    icon: 'rss_feed'
  }
]

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  }
}
</script>
