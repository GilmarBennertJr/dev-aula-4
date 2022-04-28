<template>
  <div class="container">

    <my-header v-bind:title="title"></my-header>    

    <form v-on:submit.prevent="save">
      <div class="row g-2">
        <div class="col-md-4">
          <label for="">Nome</label>
          <input type="text" class="form-control" v-model="reserva.nome" required>
        </div>

        <div class="col-3">
          <label for="">Data Reserva</label>
          <input type="date" class="form-control" v-model="reserva.dataReserva">
        </div>

        <div class="col-3">
          <label for="">Hora de Entrada</label>
          <input type="time" class="form-control" v-model="reserva.horaEntrada">
        </div>

        <div class="col-2">
          <label for="">Qtd. Horas</label>
          <input type="number" class="form-control" v-model="reserva.qtdHoras">
        </div>      

        <div class="col-4">
          <label for="">Placa</label>
          <input type="text" class="form-control" v-model="reserva.placa">
        </div>

        <div class="col-4">
          <label for="">Modelo</label>
          <input type="text" class="form-control" v-model="reserva.modelo">
        </div>

        <div class="col-4">
          <label for="">Ano</label>
          <input type="number" class="form-control" v-model="reserva.ano">
        </div>

        {{ reservas }}
  
        <div class="col-12">
          <button type="submit" class="btn btn-primary" style="margin-right: 5px">Save</button>
          <button type="button" class="btn btn-danger" @click="clear">Limpar</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  import Header from './components/header/Header.vue';

  export default {
    components: {
      'my-header': Header
    },
    data () {
      return {
        show: true,
        title: 'Cadastro e listagem de reservas',
        reserva: {nome: 'Gilmar'},
        reservas: []
      }
    },
    methods: {
      save() {
        this.reservas.push(this.reserva);
        this.reserva = {};  
      },
      clear() {
        this.reserva = {};  
      }
    }
  }
</script>