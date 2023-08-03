<template>
  <div class="user-page">
    <button type="button" class="btn btn-primary" @click="openModal">
      Детальніше
    </button>
    <ModalWindow
      v-if="isModalOpen"
      title="Користувацьке погодження"
      @close="isModalOpen = false"
    >
      <template v-slot:information>
        <div class="information">
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestiae,
            repellendus fugit. Perferendis molestiae reiciendis magni minus,
            saepe voluptatem. Laborum temporibus quas eos minus placeat saepe
            nisi nesciunt distinctio optio fugit.
          </p>
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestiae,
            repellendus fugit. Perferendis molestiae reiciendis magni minus,
            saepe voluptatem. Laborum temporibus quas eos minus placeat saepe
            nisi nesciunt distinctio optio fugit.
          </p>
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestiae,
            repellendus fugit. Perferendis molestiae reiciendis magni minus,
            saepe voluptatem. Laborum temporibus quas eos minus placeat saepe
            nisi nesciunt distinctio optio fugit.
          </p>
          <p>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Molestiae,
            repellendus fugit. Perferendis molestiae reiciendis magni minus,
            saepe voluptatem. Laborum temporibus quas eos minus placeat saepe
            nisi nesciunt distinctio optio fugit.
          </p>
        </div>
      </template>
    </ModalWindow>
  </div>
</template>

<script>
import ModalWindow from "./Modal";

export default {
  components: { ModalWindow },
  data() {
    return {
      isModalOpen: false,
    };
  },
  methods: {
    openModal() {
      this.isModalOpen = true;
    },
  },
};
</script>

<style lang="scss" scoped></style>
