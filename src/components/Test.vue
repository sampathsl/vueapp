<template>
  <div class="test">
    <h1>{{valueOne}}</h1>
    <h1>------------------------</h1>
    <span v-html="valueOne"></span>
    <h1>------------------------</h1>
    <p>{{user.firstName}}</p>
    <p>{{user.lastName}}</p>
    <h1>------------------------</h1>
    <p v-text="user.firstName"></p>
    <p v-text="user.lastName"></p>
    <h1>------------------------</h1>
    <p v-if="showFirstName">{{user.firstName}}</p>
    <h1>------------------------</h1>
    <p v-if="showLastName">{{user.lastName}}</p>
    <p v-else="showLastName">NoBody</p>
    <h1>------------------------</h1>
    <li v-for="item in items">{{item.title}}</li>
    <h1>------------------------</h1>
    <input type="text" v-model="bindingWork" placeholder="Type here"/>
    <p v-text="bindingWork"></p>
    <h1>------------------------</h1>
    <button v-on:click="greeting">Click Here</button>
    <h1>------------------------</h1>
    <button v-on:click="greetingParam('Many Greetings!')">Click Here</button>
    <h1>------------------------</h1>
    <input type="text" v-on:keyup="pressKey" placeholder="Type here"/>
    <h1>------------------------</h1>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="pressEnter" placeholder="Type here"/>
    <h1>------------------------</h1>
    <label>First Name :</label> <input type="text" v-model="user.firstName" placeholder="Type here"/>
    <br/>
    <br/>
    <label>Last Name :</label> <input type="text" v-model="user.lastName" placeholder="Type here"/>
    <br/>
    <br/>
    <label>Full Name :</label> {{this.fullName}}
  </div>
</template>

<script>
  export default {
    name : 'test',
    data() {
      return {
        valueOne : 'Hello Vue.JS',
        user : {
          firstName : 'Sampath',
          lastName : 'Test'
        },
        showFirstName : true,
        showLastName : false,
        items : [
          {title : 'Item One'},
          {title : 'Item Two'},
          {title : 'Item Three'}
        ],
        bindingWork : '',
      }
    },
    methods : {
      greeting: function () {
        alert('Many Greetings!')
      },
      greetingParam: function (message) {
        alert(message)
      },
      pressKey: function (e) {
        console.log(e.target.value)
      },
      pressEnter: function () {
        console.log('Enter pressed!')
      }
    },
    computed : {
      fullName : function () {
        return this.user.firstName + ' ' +  this.user.lastName
      }
    }
  }
</script>

<style scoped=""></style>
