<template>
    <section>
    <div class="level-face">
   <h1> MISS EBONY </h1>
    </div>
      <h2 class="repeated">REPEATED VOTES DECREASE THE USERS VOTE BY -1</h2>
  <div class="container">
    <div class="first-input">
      <input v-model="output" type="radio" value="SEWA (100L)" name="gender" id="Mr A">
     <label for="Mr A">SEWA (100L)</label>
    </div>
     <br>
    <div class="first-input">
   <input v-model="output" type="radio" value="HASSANAT (200L)" name="gender" id="MR B">
   <label for="MR B">HASSANAT (200L)</label>
   </div>
    
      
  </div>
  <div class="btn-container">
     <button @click="voteMrsEbony" class="btn">Vote</button>
    <button @click="results" class="btn">Results</button>
  </div>

   
    </section>
</template>

<script>
import { votingFireStore } from "@/firebase/config"
export default {
data() {
  return {
   output: null
  }
},
methods: {
 voteMrsEbony() {
 if (this.output === "") {
  alert("choose a candidate")
 } else {
  alert("updated")
   let mrsEbony = {
    output : this.output
  }
  this.output = ""
  votingFireStore.collection("mrsEbony").add(mrsEbony)
 }

 
},
results() {
  alert("This page is meant for the admin")
}
}
}
</script>

<style>

</style>