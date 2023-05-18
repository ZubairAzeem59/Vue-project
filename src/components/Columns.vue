import axios from 'axios';

<template>
  
  <div class="section">
    <div class="column">
      <h2>Instructions</h2>
      <p>This is some placeholder text for column 1.</p>
    </div>
    <div class="column">
      <h2>Task</h2>
      <p>This is some placeholder text for column 2.</p>
    </div>
    <div class="column ">
      <h2>Answer</h2>
      <div class="input-section">
        <textarea
          v-model="name"
          placeholder="Enter JavaScript code..."
        ></textarea>
        <button v-on:click="submitCode">Submit</button>
      </div>
    </div>
  </div>
  <div id="output"> </div><br>

 

</template>

<script>
import axios from "axios"
export default {
  name: "submitcode",
  data() {
    return {
      name: " "  
    };
  },
  methods: {
    async submitCode() {
      // Process the submitted JavaScript code here
    let result = await axios.post("http://localhost:3000/user",
    {
      name :this.name
    });
    console.warn(result);
    if(result.status==201){
      alert("submit succesfully")
    }
    }
  }

};

</script>

<style scoped>
.section {
  display: flex;
  flex-wrap: wrap;
  margin-top: 60px;
  

}

.column {
  background-color: #f1f1f1;
  padding: 20px;
  margin: 10px;
  box-sizing: border-box;
  text-align: center;
  height: 400px;
  width: 300px;
  border-radius: 12px;
  width: cal(33.3% - 20px);
  
}
.column p {
  margin-top: 20px;
}
.column h2 {
  color: rgb(22, 20, 19);
}
/* for mediam */
@media screen and (max-width:768px) {
  .column{
    width: 250px;
    height: 260px;
    
  }

.input-section textarea {
  padding: 8px;
  height: 140px;
  resize: none;
  border-radius: 4px;
  border-color: lightslategrey;
}
}

.input-section {
  margin-top: 20px;
}

textarea {
  width: 100%;
  padding: 8px 0 0 8px;
  height: 150px;
  resize: none;
  border-radius: 4px;
  border-color: lightslategrey;
}

button {
  display: block;
  margin-top: 10px;
  padding: 8px 16px;
  background-color: teal;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}
</style>
