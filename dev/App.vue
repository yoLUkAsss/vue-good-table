<template>
  <div>
    <vue-good-table
      :paginate="true"
      :columns="columns" 
      :rows="rows"
      :per-page="8"
      @current-page="pageChange">
      <template slot="table-row-before" slot-scope="props">
        <td><input type="checkbox" /></td>
      </template>
      <template slot="table-row-after" slot-scope="props">
        <td><a class="button lightbox" :href="'test_detail.php?id=' + props.row.id" >detail</a></td>
      </template>
    </vue-good-table>
  </div>
</template>

<script>
  import Vue from 'vue';
  import VueGoodTable from '../src/index';
  Vue.use(VueGoodTable);
  export default {
    name: 'test',
    data(){
      return {
        columns: [
          {
            label: '',
            sortable: false,
          },
          {
            label: 'Name',
            field: 'name',
            type: 'text',
          }, 
          {
            label: 'Age',
            field: 'age',
            type: 'number',
          }, 
          {
            label: '',
            sortable: false,
          },
        ],
        rows: [
          {
            name: "Lucas",
            age: "20"
          }, {
            name: "Pedro",
            age: "24"
          }, {
            name: "Juan",
            age: "16"
          }, {
            name: "Lucas",
            age: "20"
          }, {
            name: "Pedro",
            age: "24"
          }, {
            name: "Juan",
            age: "16"
          },{
            name: "Lucas",
            age: "20"
          }, {
            name: "Pedro",
            age: "24"
          }
        ],
      };
    },
    methods: {
      onClick() {
        console.log('clicked');
      },
      pageChange (info) {
        console.log(' pagina cambio ' + info.currentPage + ' ')
        if (info.currentPage < 1) {
          console.log(' me pase de vivaracho para atras ')
        } else {
          if (info.currentPage === 1) {
            this.rows = [{
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Juan",
              age: "16"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Juan",
              age: "16"
            },{
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Pedro",
              age: "24"
            }]
          }
          if (info.currentPage === 2) {
            this.rows = [{
              name: "Marcos",
              age: "20"
            }, {
              name: "Martin",
              age: "24"
            }, {
              name: "Maria",
              age: "16"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Juan",
              age: "16"
            },{
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }]
          }
          if (info.currentPage === 3) {
            this.rows = [{
              name: "Susana",
              age: "20"
            }, {
              name: "Silvia",
              age: "24"
            }, {
              name: "Silvina",
              age: "16"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Juan",
              age: "16"
            },{
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }]
          }
          if (info.currentPage === 4) {
            this.rows = [{
              name: "Pepe",
              age: "20"
            }, {
              name: "Pipi",
              age: "24"
            }, {
              name: "Pupu",
              age: "16"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }, {
              name: "Juan",
              age: "16"
            },{
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }]
          }
          if (info.currentPage === 5) {
            this.rows = [{
              name: "Patrick",
              age: "20"
            }, {
              name: "Jane",
              age: "24"
            }, {
              name: "Lisbon",
              age: "16"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            },{
              name: "Lucas",
              age: "20"
            }, {
              name: "Lucas",
              age: "20"
            }, {
              name: "Pedro",
              age: "24"
            }]
          }
          if (info.currentPage > 5) {
            this.rows = []
          }
        }
      }
    }
  };
</script>

<style lang="css">
  .row-style{
    background-color: red;
  }
</style>

