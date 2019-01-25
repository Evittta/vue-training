<template>
<div class="container">
  <button @click="selectedComponent = 'appQuote'">Quote</button>
  <button @click="selectedComponent = 'appAuthor'">Author</button>
  <button @click="selectedComponent = 'appNew'">New</button>
  <hr>
  <p>{{ selectedComponent }}</p>
  <keep-alive>
    <component v-bind:is="selectedComponent">
      <p>Default content</p>
    </component>
  </keep-alive>
  <app-quote>
    <h2 slot="title">{{ quoteTitle }}</h2>
    <p>I'm a slot</p>
  </app-quote>
  <app-header></app-header>
  <hr>
  <div class="row">
    <app-servers></app-servers>
    <app-server-details></app-server-details>
  </div>
  <hr>
  <app-footer></app-footer>
  <user></user>
</div>
</template>

<script>
import Header from './components/Shared/Header'
import Footer from './components/Shared/Footer'
import Servers from './components/Server/Servers'
import ServerDetails from './components/Server/ServerDetails'

import User from './components/User/User'
import Quote from './components/Quote/Quote'
import Author from './components/Quote/Author'
import New from './components/Quote/New'
export default {
  data: function() {
    return {
      quoteTitle: `I'm a quote`,
      selectedComponent: 'appQuote'
    }
  },
  components: {
    'app-header': Header,
    'app-servers': Servers,
    'app-server-details': ServerDetails,
    'app-footer': Footer,
    'user': User,
    appQuote: Quote,
    appAuthor: Author,
    appNew: New,
  }
}
</script>

<style>
</style>
