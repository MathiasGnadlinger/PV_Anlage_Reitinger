<template>
  <div>
    <HelloWorld :items="items" @update-application="updateApplication" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  setup() {
    const items = [
      {
        name: 'Maier',
        plz: '4020',
        zaehlpunkt: '0000-5232-4199-1234-0983',
        kwPeak: 14.4,
        bewilligt: true,
      },
      {
        name: 'Huber',
        plz: '4620',
        zaehlpunkt: '0000-1232-4189-1124-1983',
        kwPeak: 10.0,
        bewilligt: false,
      },
      {
        name: 'Rager',
        plz: '4400',
        zaehlpunkt: '0450-9832-4109-1764-1999',
        kwPeak: 19.0,
        bewilligt: false,
      },
    ];
    return { items };
  },
  methods: {
    updateApplication(index) {
      this.items[index].bewilligt = !this.items[index].bewilligt;
      console.log(this.items[index].bewilligt);
    },
  },
};
</script>

<style>
table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  border: 1px solid pink;
  padding: 8px;
  text-align: left;
}

th {
  background-color: pink;
  font-weight: bold;
}

tr:nth-child(even) {
  background-color: #f2f2f2;
}
</style>
