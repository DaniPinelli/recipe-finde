<template>
  <div id="finder-container" class="mt-3 background">
    <div>
      <div>
        <h1>Recipe Finder</h1>
        <input
          class="finder-placeholder mt-3"
          type="text"
          v-model="query"
          placeholder=" Type ingredient"
          v-on:input="$emit('query-change', query.toLowerCase())"
        /><br />
      </div>

      <div class="form-check form-check-inline mt-3">
        <label class="form-check-label" for="inlineRadio1">Salty</label>
        <input
          class="form-check-input"
          type="radio"
          name="inlineRadioOptions"
          v-on:input="filterSalty"
          id="inlineRadio1"
          value="Salty"
          @click="$emit('Selected-salty', salty)"
        />
      </div>
      <div class="form-check form-check-inline mt-3">
        <input
          class="form-check-input"
          type="radio"
          name="inlineRadioOptions"
          id="inlineRadio2"
          value="Sweet"
          @click="$emit('Selected-sweet', sweet)"
        />
        <label class="form-check-label" for="inlineRadio2">Sweet</label>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Finder",
  data() {
    return {
      query: "",
    };
  },
};
</script>
<style scoped>
#finder-container {
  width: 510px;
  height: 16rem;
}

.tag {
  display: flex;
}

.none {
  display: none;
}
</style>