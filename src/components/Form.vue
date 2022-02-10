<template>
    <div class="container">
        <div class="row">
            <div class="col-6 bg-light">
                <span class="fs-4">ENTRADA DE DADOS</span>
                <hr>
                <form>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Nome:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-model.lazy="form.name">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">E-mail:</label>
                        <div class="col">
                            <input type="email" class="form-control" v-model="form.email">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Senha:</label>
                        <div class="col">
                            <input type="password" class="form-control" v-model.trim="form.password">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Idade:</label>
                        <div class="col">
                            <input type="number" class="form-control" v-model="form.age">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Gênero:</label>
                        <div class="col">
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" v-model="form.gender" value="Feminino">
                                <label class="form-check-label">
                                    Feminino
                                </label>
                            </div>
                            <div class="form-check form-check-inline">
                                <input class="form-check-input" type="radio" v-model="form.gender" value="Masculino">
                                <label class="form-check-label">
                                    Masculino
                                </label>
                            </div>
                        </div>
                    </div>

                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Licença:</label>
                        <div class="col">
                            <div class="form-check form-switch">
                                <input 
                                    class="form-check-input" 
                                    type="checkbox" 
                                    v-model="form.licence"
                                    true-value="De Acordo"
                                    false-value="Não autorizo"
                                >
                                <label class="form-check-label">Li e aceito os termos</label>
                            </div>
                        </div>
                    </div>

                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Interesses:</label>
                        <div class="col">
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="JavaScript" v-model="form.interests">
                                <label class="form-check-label">
                                    JavaScript
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="VueJS" v-model="form.interests">
                                <label class="form-check-label">
                                    VueJS
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="Angular" v-model="form.interests">
                                <label class="form-check-label">
                                    Angular
                                </label>
                            </div>
                            <div class="form-check">
                                <input class="form-check-input" type="checkbox" value="NodeJS" v-model="form.interests">
                                <label class="form-check-label">
                                    NodeJS
                                </label>
                            </div>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Telefone:</label>
                        <div class="col">
                            <input type="text" class="form-control" v-model="form.tel" v-maska="'(##) #####-####'">
                            <small class="text-muted">Formato: 11 97777-5555</small>
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Data:</label>
                        <div class="col">
                            <input type="date" class="form-control" v-model="form.date">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Data/hora local:</label>
                        <div class="col">
                            <input type="datetime-local" class="form-control" v-model="form.dateHourLocal">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Mês:</label>
                        <div class="col">
                            <input type="month" class="form-control" v-model="form.month">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Semana:</label>
                        <div class="col">
                            <input type="week" class="form-control" v-model="form.week">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Hora:</label>
                        <div class="col">
                            <input type="time" class="form-control" v-model="form.hour">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Cor:</label>
                        <div class="col">
                            <input type="color" class="form-color" v-model="form.color">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Valor limite:</label>
                        <div class="col">
                            <input type="range" class="form-range" min="0" max="100" step="1" v-model="form.range">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Escondido:</label>
                        <div class="col">
                            <input type="hidden" class="form-control" v-model="form.hidden">
                        </div>
                    </div>
                    <div class="mb-3 row">
                        <label class="col-3 col-form-label">Upload:</label>
                        <div class="col">
                            <input type="file" class="form-control" multiple @change="selectFiles($event)">
                        </div>
                    </div>
                    <hr>
                    <div class="mb-3 row">
                        <div class="col d-flex justify-content-between">
                            <button class="btn btn-secondary" type="reset">Limpar</button>
                            <button class="btn btn-success" type="button">Enviar (btn)</button>
                            <button class="btn btn-success" type="submit">Enviar (submit)</button>
                        </div>                        
                    </div>
                   
                </form>
            </div>

            
            <div class="col-6 text-white bg-primary">
                <span class="fs-4">ESTADO DO OBJETO</span>
                <hr>
                <div class="mb-5 row">
                    <span>Estado do objeto</span>
                </div>

                <span class="fs-4">SAÍDA DE DADOS</span>
                <hr>
                <div class="mb-3 row">
                    <span>Nome: <span class="text-black"> {{ form.name }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>E-mail: <span class="text-black"> {{ form.email }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Senha: <span class="text-black"> {{ form.password }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Idade: <span class="text-black"> {{ form.age }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Gênero: <span class="text-black"> {{ form.gender }}  </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Licença: <span class="text-black"> {{ form.licence }}  </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Interesses: <span class="text-black"> 
                        <li v-for="(item, index) in form.interests" :key="index" class="d-inline"> {{ item + " " }} </li>    
                    </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Telefone: <span class="text-black"> {{ form.tel }}  </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Data: <span class="text-black"> {{ form.date }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Data/hora Local: <span class="text-black"> {{ form.dateHourLocal }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Mês: <span class="text-black"> {{ form.month }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Semana: <span class="text-black"> {{ form.week }}  </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Hora: <span class="text-black"> {{ form.hour }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Cor: <span :style="'color:'+form.color"> {{ form.color }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Valor Limite: <span class="text-black"> {{ form.range }}  </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Escondido: <span class="text-black"> {{ form.hidden }} </span> </span>
                </div>
                <div class="mb-3 row">
                    <span>Upload: <span class="text-black"> <ul><li style="list-style-type: none;" v-for="(item, index) in form.files" :key="index">{{item.name}}</li></ul> </span> </span>
                </div>  
            </div>
        </div>

    </div>

</template>

<script>

export default {
    name: 'Form',
    data: () => ({
        form: {
            name: '',
            email: '',
            password: '',
            age: '',
            gender: '',
            licence: '',
            interests: [],
            tel: '',
            date: '',
            dateHourLocal: '',
            month: '',
            week: '',
            hour: '',
            color: '#6c757d',
            range: '',
            hidden: '',
            files: {}
        }
    }),
    methods: {
        selectFiles(e){
            this.form.files = e.target.files
        }
    }
}
</script>