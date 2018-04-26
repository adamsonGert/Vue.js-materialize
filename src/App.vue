<template>
  <div id="app">
    <md-card>
      <md-card-header>
        <div class="md-title">Material Design with Vue.js</div>
        <div class="md-subhead">by Gert</div>
      </md-card-header>

      <md-card-content>

        <md-button class="md-raised md-primary" v-on:click="fillTable()">Fill table</md-button>
        <md-button class="md-raised md-primary" v-on:click="clearTable()">Clear table</md-button>
        <br />

        <md-table>
          <md-table-header>
            <md-table-row>
              <md-table-head>First name</md-table-head>
              <md-table-head>Last name</md-table-head>
              <md-table-head>Email</md-table-head>
            </md-table-row>
          </md-table-header>
          <md-table-body>
            <md-table-row v-for="contact in contacts">
              <md-table-cell>{{contact.firstname}}</md-table-cell>
              <md-table-cell>{{contact.lastname}}</md-table-cell>
              <md-table-cell>{{contact.email}}</md-table-cell>
            </md-table-row>
          </md-table-body>
        </md-table>
      </md-card-content>
    </md-card>
  </div>
</template>

<script>
export default {
  name: 'App',
    data: function() {
      return {
          contacts: []
      }
    },
    methods: {
      fillTable: function() {
          this.contacts.push({firstname: 'Gert', lastname: 'Adamson', email: 'gert_adamson@hotmail.com'});
          this.contacts.push({firstname: 'Juku', lastname: 'Kala', email: 'jukukala@hotmail.com'});
          this.contacts.push({firstname: 'Kati', lastname: 'Maasikas', email: 'katimaasikas9@hotmail.com'});
      },
        clearTable: function() {
          this.contacts.splice(0, this.contacts.length);
        }
    }
}
</script>

<style>
#app {
  margin-top: 60px;
  margin-left: 30px;
  margin-right: 30px;
}
</style>
