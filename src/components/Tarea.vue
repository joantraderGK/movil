<!-- eslint-disable vue/multi-word-component-names -->
<template >
    <div class="container mt-5">
        <div class="row">
            <div class="col-lg-8 offset-lg-3" >
                <input type="text" class="from-control from-control-lg " placeholder="Ingresar tarea..." 
                v-model="nombreTarea"
                v-on:keyup.enter="agregarTarea()" >
                <br>
            </div>
        </div>
        <div class="row" >
            <div class="col-lg-8.offset-lg-3">
                <div class="card p-2 " v-if="tarea.length === 0" >
                    <h6>
                       No hay tarea para mostrar  
                    </h6>
                </div>
                <ul class="list-group" v-for="(tarea, index) in tarea" v-bind:key="index" >
                    <li class="list-group-item d-flex justify-content-betweer" >
                        <spam   class="cursor" v-on:click="actualizarTarea(tarea,index)" > 
                           <i class="fa fa-circle-thin" aria-hidden="true" ></i>
                            <i  class="fa fa-check-square" aria-hidden="true"  ></i>
                        </spam>
                        <h5>
                            {{ tarea.nombre}} -{{tarea.estado  }}
                        </h5>
                        <spam class="cursor text-danger " v-on:click="eliminarTarea(index)">
                            <i class="fa fa-trash" aria-hidden="true" ></i>
                        </spam>
                    </li>
                </ul>
                </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
       return{
        tarea: [],
        nombreTarea:''
       } 
    },
    methods: {
        agregarTarea() {
            const tarea = {
                nombre: this.nombreTarea,
                estado: false
            }
           this.tarea.push(tarea);
           this.nombreTarea = '';
           console.log(this.tarea)
        },
        eliminarTarea(index) {
         this.tareas.splice(index, 1);       
        },
        actualizarTarea(tarea,index){
            this.tarea[index].estado = !tarea.estado;
        }
    }, 
  
};
</script>

<style scoped>
input {
    text-align:center;
}
.from-control-lg{
    font-size: 1.8rem;
}
.cursor{
    cursor:pointer;
}
</style>