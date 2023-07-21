<template>
  <div>
    <div>
      <img
        v-if="isCodeVisible"
        :class="imgFilters"
        :style="imgStyles"
        src="../assets/images/img.png"
        alt="Img"
      />
      <p v-else>text instead of an image</p>
    </div>

    <h2>Hide/show img</h2>
    <button @click="isCodeVisible = !isCodeVisible">Show/hide</button>

    <h2>Img filters</h2>
    <div>
      <button
        type="button"
        :class="imgFilters.sepia ? 'active' : ''"
        @click="imgFilters.sepia = !imgFilters.sepia"
      >
        Sepia
      </button>
      <button
        type="button"
        :class="imgFilters.frame ? 'active' : ''"
        @click="imgFilters.frame = !imgFilters.frame"
      >
        Frame
      </button>
      <button
        type="button"
        :class="imgFilters.shadow ? 'active' : ''"
        @click="imgFilters.shadow = !imgFilters.shadow"
      >
        Shadow
      </button>
    </div>

    <h2>Change size</h2>
    <div>
      <label>
        Height: {{ imgSizes.currentHeight }}
        <input
          type="range"
          :value="imgSizes.currentHeight"
          @input="imgSizes.currentHeight = $event.target.value"
          :min="imgSizes.minHeight"
          :max="imgSizes.maxHeight"
        />
      </label>
      <label>
        Width: {{ imgSizes.currentWidth }}
        <input
          type="range"
          :value="imgSizes.currentWidth"
          @input="imgSizes.currentWidth = $event.target.value"
          :min="imgSizes.minWidth"
          :max="imgSizes.maxWidth"
        />
      </label>
    </div>

    <h2>Rotate img</h2>
    <div>
      <input
        type="range"
        v-model.number="rotationAngle"
        min="0"
        max="360"
        step="1"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "filtersBox",
  data() {
    return {
      isCodeVisible: true,
      imgFilters: {
        sepia: false,
        frame: false,
        reduce: false,
        shadow: false,
      },
      imgSizes: {
        maxWidth: 600,
        maxHeight: 480,
        currentWidth: 600,
        currentHeight: 480,
      },
      rotationAngle: 0,
    };
  },
  computed: {
    imgStyles() {
      return {
        width: `${Math.min(
          this.imgSizes.currentWidth,
          this.imgSizes.maxWidth
        )}px`,
        height: `${Math.min(
          this.imgSizes.currentHeight,
          this.imgSizes.maxHeight
        )}px`,
        transform: `rotate(${this.rotationAngle}deg)`,
      };
    },
  },
};
</script>

<style scoped>
img {
  transition: 0.2s ease;
  &.sepia {
    filter: sepia(100%);
  }
  &.frame {
    border: 5px dashed #464646;
  }
  &.shadow {
    -webkit-box-shadow: 5px 5px 15px 5px #000000;
    box-shadow: 5px 5px 15px 5px #000000;
  }
}
button {
  margin-right: 10px;
  &.active {
    background-color: #dbdbdb;
  }
}
</style>
