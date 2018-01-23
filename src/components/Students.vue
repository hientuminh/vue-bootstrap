<template>
  <b-container fluid>
  <!-- Main table element -->
    <b-table show-empty
             stacked="md"
             :items="students"
             :fields="fields"
             :sort-by.sync="sortBy"
             :sort-desc.sync="sortDesc">
      <template slot="actions" slot-scope="row">
        <!-- We use @click.stop here to prevent a 'row-clicked' event from also happening -->
        <b-button size="sm" variant="success" @click="info(row.item, row.index)" class="mr-1">
          Info modal
        </b-button>
        <b-button size="sm" variant="warning" @click="follow(row.item, row.index)">
          Follow
        </b-button>
        <b-button size="sm" variant="danger" @click="remove(row.item, row.index)">
          Remove
        </b-button>
      </template>
    </b-table>
    {{modalInfo}}
    <information-modal :information-data.sync="modalInfo"></information-modal>
  </b-container>
</template>

<script>
import InformationModal from '@/components/InformationModal'
export default {
  name: 'Students',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      students: [
        {
          id: 1,
          name: 'Tu Minh Hien',
          birthday: '8/30/1989',
          toan: 9,
          ly: 7,
          hoa: 4
        },
        {
          id: 2,
          name: 'Tran Thanh Tuan',
          birthday: '2/22/1994',
          toan: 6,
          ly: 7,
          hoa: 9
        },
        {
          id: 3,
          name: 'Nguyen Cong Phuong',
          birthday: '9/5/1992',
          toan: 9,
          ly: 9,
          hoa: 6
        }
      ],
      fields: [
        { key: 'id', label: 'ID', sortable: true },
        { key: 'name', label: 'Person Full name', sortable: true },
        { key: 'birthday', label: 'Birthday', sortable: true, 'class': 'text-center' },
        { key: 'toan', sortable: true },
        { key: 'hoa', sortable: true },
        { key: 'ly', sortable: true },
        { key: 'actions', label: 'Actions' }
      ],
      sortBy: null,
      sortDesc: false,
      modalInfo: {}
    }
  },
  methods: {
    info: function (item, index) {
      this.modalInfo = item
      this.$root.$emit('bv::show::modal', 'modalInfoID', 'showModal')
    },
    remove: function (item, index) {
    },
    follow: function (item, index) {
    }
  },
  components: {
    'information-modal': InformationModal
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
