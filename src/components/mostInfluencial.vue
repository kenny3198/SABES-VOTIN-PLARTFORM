<template>
    <section>
    <div class="level-face">
   <h1>MOST INFLUENCIAL </h1>
    </div>
     <h2 class="repeated">REPEATED VOTES DECREASE THE USERS VOTE BY -1</h2>
  <div class="container">
    <div class="first-input">
      <input v-model="output" type="radio" value="DAMZY (300L)" name="gender" id="Mr A">
     <label for="Mr A">DAMZY (300L)</label>
    </div>
     <br>
    <div class="first-input">
   <input v-model="output" type="radio" value="MICKY (300L)" name="gender" id="MR B">
   <label for="MR B">MICKY (300L)</label>
   </div>
    <br>
   <div class="first-input">
    <input v-model="output" type="radio" value="GT (500L)" name="gender" id="MR C">
    <label for="MR C">GT (500L)</label>
    </div>
  <br>
  <div class="first-input">
     <input v-model="output" type="radio" value="PATO (400L)" name="gender" id="MR D">
     <label for="MR D">PATO (400)</label>
     </div>
     <br>
      <div class="first-input">
      <input v-model="output" type="radio" value="JUDE (500L)" name="gender" id="MR E">
      <label for="MR E">JUDE (500)</label>
      </div>
      <br>
  </div>
  <div class="btn-container">
     <button @click="voteMostInfluencial" class="btn">Vote</button>
    <button  @click="results" class="btn"> Results</button>
  </div>
    </section>
</template>

<script>
import { votingFireStore } from "@/firebase/config"
export default {
data() {
  return {
   output: null,
    
  }
},
methods: {
voteMostInfluencial() {
  if (this.output === "") {
    alert("chose a candidate")
  } else {
    alert("updated")
    let influencialVote = {
    output : this.output
  }
  this.output = ""
  votingFireStore.collection("influencialVote").add(influencialVote)
  }
},
results() {
  alert("this page is meant for the admin")
}
},

}
</script>

<style>
img{
  width: 20px;
  display: flex;
  align-items: center;
}
</style>