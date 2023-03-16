<template>
    <h1 ref="header">Home</h1>
    <h3>MY {{ name }} a : {{ age }} </h3>
    <input type="text" v-model="name">
    <p>{{ personne1.name }}</p>
    <p>{{ personne2.name }}</p>
    <input type="text" v-model="search">
    {{ search }}
    <div v-for="courses in result" :key="courses.id">
      {{ courses }}
    </div>
    <button @click="age++">clicker</button>
    <button @click="sayHallo">clicker</button>
    <button @click="handleWatch">stop</button>


    
</template>

<script>
// ref = used for variable and chaine carctere  and rectivie used for table and objects
import {ref,reactive,computed,watch,watchEffect} from 'vue'
export default {
  name: 'Home',
  setup(){

    let header=ref(null);
      // my data
    let name=ref("Abdo");
    let age=ref("26");
    // return {name:name,age:age}
    // my method 
    let personne1= ref({name:"ali",age:3});
    let personne2= reactive({name:"ahmed",age:3});
    const search=ref('');
    let courses=ref(['java','angular js','vus js','react js']);
    // computed
    const result = computed( () => {
      return courses.value.filter(course => course.includes (search.value))
      });
    // watch
    const stopWatch=watch(search,()=>{
      console.log('i watch',search.value)
    })
    // watchEffect
    const stopWatchEffect=watchEffect(()=>{
      console.log('watch efffect',search.value)
    })

  

    const sayHallo=()=>{

      console.log(header.value)
      header.value.classList.add('my-2')
      header.value.textContent = "Welcom to blog"
      name.value="waldi";
      personne1.value.name="basma";
      personne2.name="omar";      
    }
    const handleWatch=()=>{
        stopWatch(),
        stopWatchEffect()
    }
 
    // 
    
    return {name, age, sayHallo, header, personne1,personne2,courses,search,result,handleWatch}

  }


}
</script>
