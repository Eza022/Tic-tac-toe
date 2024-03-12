 <template>
  <div id="board">
    <div class="square" v-for="n in 9" v-bind:key="n" @click="clickedSquare(this)"> 
      {{ square [n] }}
    </div>
  </div>
  <div id="app">
   
  </div>
</template> 

<script>
import {ref} from "vue";
export default {
  name: 'App',
 setup(){
  let currentTurn = "X";
  let square =ref([]);
  for (let i=0; i<=9; i++) square.value.push(null);

  function clickedSquare(){
    currentTurn === "X" ? (currentTurn = "O") : (currentTurn = "X");
    console.log(currentTurn);
  }
  return {square, clickedSquare };
 },
}; 
</script> 

<style>
#board {
  height: 400px;
  width: 400px;
  margin: 0 auto;
  display:flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.square{
  width: 30%;
  background-color: gray;
  border: 1px solid black;
}
</style>
