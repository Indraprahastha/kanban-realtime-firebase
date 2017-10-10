<template>
  <div class="col-md-3">
    <div class="utama">
      <h3>Doing</h3>
    </div>
    <div v-for="data in semuadoing" class="pad">
      <div class="bar">

        <table class="table table-striped">
          <tr>
            <th class="tab">Judul :</th>
            <td class="tab1">{{data.judul}}</td>
          </tr>
          <tr>
            <th class="tab">Deskripsi :</th>
            <td class="tab1">{{data.deskripsi}}</td>
          </tr>
          <tr>
            <th class="tab">Poin :</th>
            <td class="tab1">{{data.poin}}</td>
          </tr>
          <tr>
            <br>
          </tr>
          <tr>
            <th class="tab"><button type="button" @click="hapus(data['.key'])">delete</button></th>
            <td class="tab1"><button type="button" @click="pindah(data['.key'],data.judul,data.deskripsi,data.poin)">Go Done</button></td>
          </tr>
        </table>

      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Doing',
  data () {
    return {
    }
  },
  firebase: function () {
    return {
      semuadoing: this.$db.ref('kanban/doing/')
    }
  },
  created () {
    console.log(this.semuadoing)
  },
  methods: {
    hapus (id) {
      this.$db.ref(`kanban/doing/` + id).remove()
    },
    pindah (id, judul, deskripsi, poin) {
      this.$db.ref('kanban/done/').push({
        judul: judul,
        deskripsi: deskripsi,
        poin: poin
      })
      this.$db.ref(`kanban/doing/` + id).remove()
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.col-md-3 {
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 25px;
  border: 1px solid #ffffff;
  /*margin-right: 1px;*/
}
.container {
  padding-top: 50px;
  margin-left: auto;
  margin-right: auto;
  font-family: Lobster;
}
.legend {
  font-family: 'Lobster', cursive;
}
.bar {
  font-size: 10px;
  text-align: justify;
  background-color: rgba(255, 0, 0, 0.3);
}
.pad {
  margin-bottom: 20px;
}
.tab {
  width: 50%;
}
.tab1 {
  width: 50%;
  text-align: right;
}
.utama {
  text-align: center;
}
</style>
