<template>
  <q-card>
    <q-list bordered class="rounded-borders text-primary">
      <q-item
        v-for="(item, idx) in router_table"
        :key="idx"
        clickable
        v-ripple
        :active="link === 'inbox'"
        :to="item.path"
        exact
        active-class="my-menu-link"
      >
        <q-item-section avatar>
          <q-icon :name="item.icon" />
        </q-item-section>

        <q-item-section>{{ item.name }}</q-item-section>
      </q-item>
    </q-list>
  </q-card>
</template>

<script setup>
import { ref } from "vue";
const link = ref("inbox");
const router_table = [
  {
    icon: "add",
    name: "home",
    path: "/home",
  },
  {
    icon: "add",
    name: "斗地主",
    path: "/doudizhu",
  },
];
</script>

<style lang="scss">
.my-menu-link {
  color: white;
  background: #f2c037;
}
</style>
