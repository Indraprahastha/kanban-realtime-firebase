<template>
  <div class="hello container">
    <formulir/>
    <div class="tercatat">
      <Backlock/>
      <Todo/>
      <Doing/>
      <Done/>
    </div>
  </div>
</template>

<script>
import Backlock from './Backlock'
import Formulir from './Formulir'
import Todo from './Todo'
import Doing from './Doing'
import Done from './Done'
export default {
  name: 'HelloWorld',
  data () {
    return {

    }
  },
  components: {
    Formulir,
    Backlock,
    Todo,
    Doing,
    Done
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  font-family: 'Nosifer', cursive;
  padding-bottom: 30px;
}
.tercatat {
  padding-top: 20px;
}
.pad {
  padding-left: 5px;
}
</style>
