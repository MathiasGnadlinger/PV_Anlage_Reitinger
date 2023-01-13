<template>
  <div>
    <h1>PV-Förderung</h1>
    <p>
      PV - FördererungenEAG-Investitionszuschuss Photovoltaik und Stromspeicher
      im Jahr 2023Mit dem Erneuerbaren-Ausbau-Gesetz (EAG) wurden die
      rechtlichen Rahmenbedingungen für den Netzanschluss von erneuerbaren
      Energieanlagen vereinfacht. Dies umfasst auch finanzielleErleichterungen
      in Form eines pauschalierten Netzzutrittsentgelts. Mit einem der
      EAG-Investitionszuschüsse werden die Neuerrichtung und Erweiterung von
      Photovoltaikanlagen und die damit verbundene Neuerrichtung von
      Stromspeichern gefördert. Für die Erweiterung einer Photovoltaikanlage ist
      keine Mindestgröße vorgesehen.
    </p>
    <h1>Bisherige Ansuchen (Max. Fördersumme: €10000000)</h1>
    <div>
      <table>
        <thead>
          <th>Name:</th>
          <th>PLZ:</th>
          <th>Zählpunkt:</th>
          <th>kwPeak:</th>
          <th>Bewilligt:</th>
        </thead>
        <tbody>
          <tr v-for="(item, index) in items" :key="item.zaehlpunkt">
            <td>
              {{ item.name }}
            </td>
            <td>
              {{ item.plz }}
            </td>
            <td>
              {{ item.zaehlpunkt }}
            </td>
            <td>
              {{ item.kwPeak }}
            </td>
            <td>
              <input
                type="checkbox"
                v-model="isChecked"
                @change="updateBewilligt(index)"
              />
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    items: { type: Array, required: true },
  },
  methods: {
    updateBewilligt(index) {
      //Hier kann man die Änderungen an "bewilligt" speichern oder entsprechend verarbeiten
      //zB:
      // axios.patch('/api/items/' + item...
      //andere update Logic
      this.$emit('update-application', index);
    },
  },
};
</script>
