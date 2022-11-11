<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        />
        <q-input filled bottom-slots v-model="myKey" label="關鍵字查詢">
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
        <q-toolbar-title>
          造型氣球
        </q-toolbar-title>

        <div>第1.2版</div>
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
          項目
        </q-item-label>
        <q-item to = "/">影音</q-item>
        <q-item to = "/book">書籍</q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view :myKey="myKey" />
    </q-page-container>
  </q-layout>
</template>

<script>

export default {
  name: 'MainLayout',
  data () {
    return {
      myKey: '',
      leftDrawerOpen: false
    }
  }
}
</script>
