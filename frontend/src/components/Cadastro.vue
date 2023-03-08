<template>
    <form class="row g-3 mt-4">
        <div class="col-md-12 row d-flex justify-content-center">
            <img src="https://mdbcdn.b-cdn.net/img/new/avatars/2.webp" class="rounded-circle" style="width: 150px;"
  alt="Avatar" />

            <div class="mb-3 mt-2">
                <input class="form-control" type="file" id="formFile">
            </div>
        </div>

        <div class="col-md-6">
            <label for="exampleFormControlInput1" class="form-label">Nome Completo:</label>
            <input type="text" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">
        </div>
        <div class="col-md-6">
            <label for="exampleFormControlTextarea1" class="form-label">RG:</label>
            <input class="form-control" id="exampleFormControlTextarea1" rows="3" />
        </div>
        <div class="col-md-6">
            <label for="exampleFormControlTextarea1" class="form-label">CPF:</label>
            <input class="form-control" id="exampleFormControlTextarea1" rows="3" />
        </div>
        <div class="col-md-6">
            <label for="exampleFormControlTextarea1" class="form-label">Data de Nascimento:</label>
            <input class="form-control" id="exampleFormControlTextarea1" rows="3" />
        </div>
        <div class="col-md-6">
            <label for="exampleFormControlTextarea1" class="form-label">Estado Civil:</label>
            <input class="form-control" id="exampleFormControlTextarea1" rows="3" />
        </div>
        <div class="col-md-6">
            <label for="exampleFormControlTextarea1" class="form-label">Telefone:</label>
            <input class="form-control" id="exampleFormControlTextarea1" rows="3" />
        </div>

        <div class="col-md-6">
            <label for="inputCity" class="form-label">Data do Batismo:</label>
            <input type="text" class="form-control" id="inputCity">
        </div>
        <div class="col-md-6">
            <label for="inputCity" class="form-label">Cargo Eclesiástico:</label>
            <input type="text" class="form-control" id="inputCity">
        </div>
        <div class="col-md-6">
            <label for="inputCity" class="form-label">Nome do Pai:</label>
            <input type="text" class="form-control" id="inputCity">
        </div>
        <div class="col-md-6">
            <label for="inputCity" class="form-label">Nome da Mãe:</label>
            <input type="text" class="form-control" id="inputCity">
        </div>

         <div class="col-md-6">
            <label for="inputZip" class="form-label">CEP:</label>
            <input @keyup="getCep()" v-model="cep" type="text" class="form-control" id="inputZip">
        </div>

        <div v-if="data !== null" class="row g-3">
            <div class="col-md-6" :v-if="index !== 'cep'" v-for="(value, index) in data" :key="index">
                <label for="" class="form-label">{{ index.toUpperCase() }}</label>
                <input 
                    class="form-control"
                    :placeholder="index"
                    v-model="data[index]"
                    type="text"
                />
            </div>
        </div>
  
        
        <div class="col-12">
            <button type="submit" class="btn btn-primary">Cadastrar</button>
        </div>
    </form>
</template>

<script>
import axios from 'axios';
export default {
    name: 'Cadastro',
    data() {
        return {
            cep: '',
            data : null,
		    messageCep: null
        }
    },
    methods: {
        getCep() {
            if(this.cep.length == 8) {
				axios.get(`https://viacep.com.br/ws/${this.cep}/json/`)
				.then( response => {
                    this.data = response.data 
                })
				.catch( error => console.log(error) )
			}
        }
    }
}
</script>

<style scoped>

</style>