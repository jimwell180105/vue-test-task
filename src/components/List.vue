<template>
  <div class="container">
    <div class="row">
      <div class="col-sm">
        <v-data-table
          :headers="headers"
          :items="listData"
          class="elevation-1"
        >
          <template slot="items" slot-scope="users">
            <td>{{ users.item.id }}</td>
            <td>{{ users.item.name }}</td>
            <td>{{ users.item.username }}</td>
            <td>{{ users.item.email }}</td>
            <td>{{ users.item.address.street+' '+users.item.address.suite+' '+users.item.address.city }}</td>
            <td>{{ users.item.address.zipcode }}</td>
            <td>{{ users.item.phone }}</td>
            <td>{{ users.item.website }}</td>
            <td>{{ users.item.company.name }}</td>
            <td>{{ users.item.company.catchPhrase }}</td>
            <td>{{ users.item.company.bs }}</td>
          </template>
        </v-data-table>
      </div>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'List',
  data () {
    return {
      listData: {},
      headers: [
        { text: 'Id', value: 'id' },
        { text: 'Name', value: 'name' },
        { text: 'Username', value: 'username' },
        { text: 'Email', value: 'email' },
        { text: 'Address', value: 'address' },
        { text: 'Zipcode', value: 'zipcode' },
        { text: 'phone', value: 'phone' },
        { text: 'Website', value: 'website' },
        { text: 'Company Name', value: 'company-name' },
        { text: 'Catchphrase', value: 'company-catchphrase' },
        { text: 'BS', value: 'company-bs' }
      ]
    }
  },
  methods: {
    getList: function () {
      const _this = this
      axios.get('https://jsonplaceholder.typicode.com/users')
        .then((response) => {
          _this.listData = response.data
        }, (error) => {
          console.log(error)
        })
    }
  },
  beforeMount () {
    this.getList()
  }
}
</script>
