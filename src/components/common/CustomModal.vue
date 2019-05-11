<template>
  <b-modal
    :id="idModal"
    title="Add a new book"
    hide-footer
    :class="{ 'hide-modal': isHide }"
  >
    <b-form
      @submit="onSubmit"
      @reset="onReset"
      class="w-100"
    >
      <b-form-group
        id="form-title-group"
        label="Title:"
        label-for="form-title-input"
      >
        <b-form-input
          id="form-title-input"
          type="text"
          v-model="title"
          required
          placeholder="Enter title"
        >
        </b-form-input>
      </b-form-group>
      <b-form-group
        id="form-author-group"
        label="Author:"
        label-for="form-author-input"
      >
        <b-form-input
          id="form-author-input"
          type="text"
          v-model="author"
          required
          placeholder="Enter author"
        >
        </b-form-input>
      </b-form-group>

      <b-form-group id="form-read-group">
        <b-form-checkbox-group
          v-model="read"
          id="form-checks"
        >
          <b-form-checkbox
            value="true"
          >
            Read?
          </b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group>

      <b-button
        type="submit"
        variant="primary"
      >
        Submit
      </b-button>
      <b-button
        type="reset"
        variant="danger"
      >
        Reset
      </b-button>

    </b-form>
  </b-modal>
</template>

<script>
export default {
  name: 'CustomModal',
  props: {
    onSubmit: Function,
    onReset: Function,
    title: String,
    author: String,
    read: Array,
    isHide: Boolean,
    idModal: String,
  },
}
</script>

<style scoped>
  .hide-modal {
    display: none;
  }
</style>
