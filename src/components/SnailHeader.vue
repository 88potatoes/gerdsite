<template>
    <header>
       <!-- Your header content goes here -->
       <nav>
         <ul>
           <li><a href="#">Home</a></li>
           <li><a href="#">About</a></li>
           <li><a href="#">Contact</a></li>
         </ul>
       </nav>
    </header>
   </template>
   
   <script>
   export default {
    name: 'SnailHeader',
    data() {
       return {
         // Add any data properties you need for your header
       };
    },
    methods: {
       // Add methods for handling events in your header
    },
   };
   </script>
   
   <style scoped>
   /* Add your CSS styles for the SnailHeader component here */
   header {
    background-color: #f8f9fa;
    padding: 10px;
   }
   
   nav ul {
    list-style-type: none;
    padding: 0;
   }
   
   nav ul li {
    display: inline;
    margin-right: 10px;
   }
   
   nav ul li a {
    text-decoration: none;
    color: #333;
   }
   </style>
   