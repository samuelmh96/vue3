<template>
    <section>
        <h3>Add Teacher</h3>
        <div><label>Name:<input type="text" v-model="teacher.name"></label></div>
        <div><label>LastName:<input type="text" v-model="teacher.lastname"></label></div>
        <div><label>DNI / NIF:<input type="text" v-model="teacher.dni"></label></div>
        <div><label>Courses:<input type="text" v-model="subject"></label> <button @click="handleSubject()">Add</button></div>
        <div>
            <ul>
                <li v-for="(elm,index) in teacher.subjects" :key="index">{{elm.name}}</li>
            </ul>
        </div>
        <input type="checkbox" v-model="teacher.doc">Documentation submitted
        <button @click="handleAddTeacher()">Add</button>
    </section>
    <section>
        <h3>List of teachers</h3>
        <table border="1">
            <tr>
                <th>Name</th>
                <th>Last Name</th>
                <th>DNI/NIF</th>
                <th>Courses</th>
                <th>Document</th>
            </tr>
            <tr v-for="t in teachers" :key="t.dni">
                <th>{{t.name}}</th>
                <td>{{t.lastname}}</td>
                <td>{{t.dni}}</td>
                <th>
                    <ul>
                        <li v-for="(m, index) in t.subjects" :key="index">{{m.name}}</li>
                    </ul>
                </th>
                <th v-if="t.doc">Entregado</th>
                <th v-else>No Entregado</th>
            </tr>
        </table>
    </section>
</template>
<script lang="ts" setup>
import { Ref, ref } from "vue";

interface ISubject {
  name: string;
}

interface ITeacher {
  name: string;
  lastname: string;
  dni: string;
  subjects: ISubject[];
  doc: boolean;
}

let teacher: Ref<ITeacher> = ref({
  name: '',
  lastname: '',
  dni: '',
  subjects: [],
  doc: false,
});

let subject: Ref<string> = ref('');

const handleSubject = () => {
  const newSubject: ISubject = { name: subject.value };
  teacher.value.subjects.push(newSubject);
  subject.value = '';
};

const teachers: Ref<ITeacher[]> = ref([]);
    
const handleAddTeacher = () => {
  teachers.value.push({ ...teacher.value });
  teacher.value = {
    name: '',
    lastname: '',
    dni: '',
    subjects: [],
    doc: false,
  };
};
</script>

<style scoped>
  section {
    margin-bottom: 20px;
    transition: margin 0.3s ease-in-out;
  }

  h3 {
    font-size: 1.5rem;
    margin-bottom: 10px;
    transition: margin-bottom 0.3s ease-in-out;
  }

  label {
    display: block;
    margin-bottom: 5px;
  }

  input {
    padding: 5px;
    margin-bottom: 10px;
    transition: margin 0.3s ease-in-out;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    margin-bottom: 5px;
    transition: margin 0.3s ease-in-out;
  }

  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 10px;
    transition: margin 0.3s ease-in-out;
  }

  th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: left;
    transition: background-color 0.3s ease-in-out;
  }

  th {
    background-color: #f2f2f2;
  }

  button {
    padding: 8px 12px;
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out;
  }

  button:hover {
    background-color: #45a049;
  }

  input[type="checkbox"] {
    margin-right: 5px;
  }

  button, input[type="text"] {
    outline: none;
  }

  button:focus, input[type="text"]:focus {
    border: 2px solid #4CAF50;
  }

</style>
