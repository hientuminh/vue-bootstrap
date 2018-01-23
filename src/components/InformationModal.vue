<template lang="html">
  <b-modal id="modalInfoID" :title="msg" @ok="handleOk">
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Name:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="text" v-model="modalData.name"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Birthday:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="text" v-model="modalData.birthday" disabled></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Toan:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="number" v-model.number="modalData.toan"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Ly:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="number" v-model.number="modalData.ly"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Hoa:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="number" v-model.number="modalData.hoa"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Sum:</label></b-col>
      <b-col sm="10">
        <b-form id="input-small" size="sm" type="number">{{diemtrungbinh | round(2)}}</b-form>
      </b-col>
    </b-row>
  </b-modal>
</template>

<script>
export default {
  name: 'InformationModal',
  props: ['information'],
  data: function () {
    return {
      msg: 'Information',
      modalData: this.information
    }
  },
  watch: {
    information: function () {
      this.modalData = this.deepCopy(this.information)
    }
  },
  methods: {
    deepCopy: function (obj) {
      return JSON.parse(JSON.stringify(obj))
    },
    handleOk: function () {
      this.$emit('update-profile', this.modalData)
    }
  },
  computed: {
    diemtrungbinh: function () {
      console.log(this.modalData)
      return (this.modalData.toan + this.modalData.ly + this.modalData.hoa) / 3
    }
  },
  filters: {
    round: function (value, decimals) {
      if (!value) {
        value = 0
      }

      if (!decimals) {
        decimals = 0
      }

      value = Math.round(value * Math.pow(10, decimals)) / Math.pow(10, decimals)
      return value
    }
  }
}
</script>

<style lang="css">
</style>
