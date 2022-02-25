<template>
  <div class="body">
    <header>
      <h1>My Marathon Check List</h1>
      <img
        src="./assets/jogging-2343558_1280.webp"
        alt="Coureur"
      />
    </header>
    <main>
      <div class="add">
        <input v-model="newStuff" @keyup.enter="addStuff" />
        <button @click="addStuff">Add Stuff</button>
      </div>
      <section class="list">
        <ul>
          <li v-for="stuff in stuffs" :key="stuff.id">
            <input type="checkbox" v-model="stuff.done" />
            <span :class="{ done: stuff.done }">{{ stuff.text }}</span>
          </li>
        </ul>
        <img src="./assets/YoungGrossHoopoe-max-1mb.gif" />
      </section>
      <p>created on February 25, 2022 by Julien Tomada </p>
    </main>
  </div>
</template>

<script>
let id = 0
export default {
  data() {
    return {
      newStuff: '',
      stuffs: [
        { id: id++, text: 'Shoes' },
        { id: id++, text: 'Short' },
        { id: id++, text: 'Tee-shirt' },
        { id: id++, text: 'Socks' },
        { id: id++, text: 'Watch' }
      ]
    }
  },
  methods: {
    addStuff() {
      this.stuffs.push({ id: id++, text: this.newStuff })
      this.newStuff = ''
    },
    removeStuff(stuff) {
      this.stuffs = this.stuffs.filter((el) => el !== stuff)
    },   
  } 
}
</script>

<style scoped>
.body {
  width: 500px;
  margin: auto;
  background-color: rgb(247, 239, 231);
  border-radius: 10px;
}
@import url("https://fonts.googleapis.com/css2?family=Shizuru&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@300&display=swap");
@import url(https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css);
header {
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: rgb(206, 197, 197);
  border-radius: 10px;
}
header img {
  width: 500px;
  height: 200px;
  border-radius: 0 0 10px 10px;
}
h1 {
  color: rgb(10, 59, 59);
  font-family: "Shizuru", cursive;
  font-size: 30px;
}
.add {
  margin: 20px 10px 0;
  display: flex;
  justify-content: right;
  position: relative;
}
.add input {
  width: 250px;
  height: 30px;
  background-color: rgb(143, 141, 141);
  border-radius: 10px;
  border: 0.5px solid rgb(235, 215, 215);
  margin: 0 10px;
  color: antiquewhite;
  padding: 0 10px;
  font-family: "Nunito", sans-serif;
  font-weight: bold;
}
.add button {
  border-radius: 10px;
  border: 0.5px solid rgb(206, 197, 197);
  background-color: rgb(206, 197, 197);
  color: rgb(10, 59, 59);
  font-family: "Nunito", sans-serif;
  font-weight: bold;
}
.list {
  border: 1px solid rgb(228, 196, 156);
  margin: 30px 10px;
  position: relative;
}
.list li {
  font-family: "Nunito", sans-serif;
  font-weight: bold;
  font-size: 20px;
  list-style: none;
  margin-left: 60px;
  padding: 2px;
  position: relative;
}
.list img {
  width: 50px;
  height: 50px;
  position: absolute;
  right: 80px;
  top: 50px;
  border-radius: 10px;
}
input[type="checkbox"] {
  -webkit-appearance: none;
  -moz-appearance: none;
  -ms-appearance: none;
}
input[type="checkbox"] {
  border-radius: 4px;
  height: 15px;
  width: 15px;
  background: #fff;
  border: 1px solid #ccc; 
  margin-right: 10px; 
  position: absolute;
  top: 5px;
  left: -25px
}
input[type="checkbox"]:checked {
    background: rgb(87, 87, 2);     
}
p{
  font-family: "Nunito", sans-serif;
  font-weight: bold;
  font-size: 8px;
  text-align: right;
  padding: 20px;
}


</style>

