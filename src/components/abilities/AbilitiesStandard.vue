<template>
  <div class="abilities-standard">
    <abilities-array :abilitiesArray="abilitiesStandardArray" :pickedUpScore="pickedUpScore" :dropedScoreIndex="dropedScoreIndex" @scorePickedUp="pickedUpScore=$event" @resetScores="resetScores"></abilities-array>
    <ability-scores-form :pickedUpScore="pickedUpScore" :abilityScoresProp="abilityScores" @scoreDropped="dropScore($event)"></ability-scores-form>
  </div>
</template>

<script>
import AbilityScoresForm from './AbilityScoresForm.vue';
import AbilitiesArray from './AbilitiesArray.vue';
export default {
  components: {
    AbilityScoresForm,
    AbilitiesArray
  },
  data() {
    return {
      abilitiesStandardArray: [15, 14, 13, 12, 10, 8],
      pickedUpScore: 0,
      dropedScoreIndex: [],
      abilityScores: {
        str: "",
        dex: "",
        con: "",
        int: "",
        wis: "",
        cha: ""
      }
    }
  },
  methods: {
    dropScore(index) {
      this.pickedUpScore = 0;
      this.dropedScoreIndex.push(index);
    },
    resetScores() {
      this.dropedScoreIndex = [];
      this.abilityScores = {
        str: "",
        dex: "",
        con: "",
        int: "",
        wis: "",
        cha: ""
      }
    }
  }
}
</script>

