<template lang="html">
  <b-modal id="modalInfoID" :title="msg" ok-only>
    {{modalData}}
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
        <b-form-input id="input-small" size="sm" type="text" v-model="modalData.toan" disabled></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Ly:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="text" v-model="modalData.ly" disabled></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Hoa:</label></b-col>
      <b-col sm="10">
        <b-form-input id="input-small" size="sm" type="text" v-model="modalData.hoa" disabled></b-form-input>
      </b-col>
    </b-row>
    <!-- <b-row class="my-1">
      <b-col sm="2"><label for="input-small">Sum:</label></b-col>
      <b-col sm="10">
        <b-form id="input-small" size="sm" type="number">{{diemtrungbinh}}</b-form>
      </b-col>
    </b-row> -->
  </b-modal>
</template>

<script>
export default {
  name: 'InformationModal',
  props: ['informationData'],
  data: function () {
    return {
      msg: 'Information',
      modalData: this.informationData
    }
  },
  beforeUpdate () {
    this.modalData = Object.assign({}, this.informationData)
  }
  // methods: {
  //   deepCopy: function (obj) {
  //     return JSON.parse(JSON.stringify(obj))
  //   }
  // },
  // computed: {
  //   diemtrungbinh () {
  //     return this.informationData
  //   }
  // }
}
</script>

<style lang="css">
</style>
