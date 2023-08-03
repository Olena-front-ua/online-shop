<template>
  <div class="modal fade show" ref="modalWindow">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title">
            {{ title }}
          </h5>
          <button
            type="button"
            class="close"
            aria-label="Close"
            @click="closeModal"
          >
            <span aria-hidden="true">&times;</span>
          </button>
        </div>
        <div class="modal-body" @scroll="onScroll">
          <slot name="information"></slot>
        </div>
        <div class="modal-footer">
          <slot name="footer">
            <button type="button" class="btn btn-secondary" @click="closeModal">
              Відміна
            </button>
            <button
              type="button"
              class="btn btn-primary"
              :disabled="!isRulesRead"
            >
              Прийняти
            </button>
          </slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalWindow",
  props: {
    title: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      isRulesRead: false,
    };
  },
  // beforeCreate() {
  //   console.log("beforeCreate");
  // },
  mounted() {
    const modalBody = this.$refs.modalWindow.querySelector(".modal-body");
    modalBody.scrollTop = modalBody.scrollHeight - modalBody.clientHeight;
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
    onScrollEnd() {
      this.isRulesRead = true;
    },
    // onBodyScroll() {
    //   const modalBody = this.$refs.modalBody;
    //   if (
    //     modalBody.clientHeight + modalBody.scrollTop >=
    //     modalBody.scrollHeight
    //   ) {
    //     this.isRulesRead = true;
    //   }
    // },
  },
  created() {
    this.$log();
  },
};
</script>

<style scoped>
.modal {
  display: block;
  .modal-body {
    height: 200px;
    overflow-y: scroll;
  }
}
</style>
