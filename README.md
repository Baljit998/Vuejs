## Learn vue.js

Can use with CDN without installing but not a good approach.
Now install node js https://nodejs.org/en/download/
npm is installed by default.
Install vue 
```
npm install -g @vue/cli
```
Now run in vue tut folder
```
vue create blog
```
Access locally 
```
Microsoft Windows [Version 10.0.19045.3803]
(c) Microsoft Corporation. All rights reserved.

C:\Users\User\Desktop\vue tut>vue create blog
?  Your connection to the default npm registry seems to be slow.
   Use https://registry.npmmirror.com for faster installation? Yes


Vue CLI v5.0.8
? Please pick a preset: Default ([Vue 3] babel, eslint)


Vue CLI v5.0.8
✨  Creating project in C:\Users\User\Desktop\vue tut\blog.
⚙️  Installing CLI plugins. This might take a while...


added 866 packages in 2m
🚀  Invoking generators...
📦  Installing additional dependencies...


added 103 packages in 19s
⚓  Running completion hooks...

📄  Generating README.md...

🎉  Successfully created project blog.
👉  Get started with the following commands:

 $ cd blog
 $ npm run serve


C:\Users\User\Desktop\vue tut>code .
'code' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut>cd blog

C:\Users\User\Desktop\vue tut\blog>code .
'code' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>sudo code .
'sudo' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>gsudo code .
'gsudo' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\User\Desktop\vue tut\blog>runas code .
RUNAS USAGE:

RUNAS [ [/noprofile | /profile] [/env] [/savecred | /netonly] ]
        /user:<UserName> program

RUNAS [ [/noprofile | /profile] [/env] [/savecred] ]
        /smartcard [/user:<UserName>] program

RUNAS /trustlevel:<TrustLevel> program

   /noprofile        specifies that the user's profile should not be loaded.
                     This causes the application to load more quickly, but
                     can cause some applications to malfunction.
   /profile          specifies that the user's profile should be loaded.
                     This is the default.
   /env              to use current environment instead of user's.
   /netonly          use if the credentials specified are for remote
                     access only.
   /savecred         to use credentials previously saved by the user.
   /smartcard        use if the credentials are to be supplied from a
                     smartcard.
   /user             <UserName> should be in form USER@DOMAIN or DOMAIN\USER
   /showtrustlevels  displays the trust levels that can be used as arguments
                     to /trustlevel.
   /trustlevel       <Level> should be one of levels enumerated
                     in /showtrustlevels.
   program         command line for EXE.  See below for examples

Examples:
> runas /noprofile /user:mymachine\administrator cmd
> runas /profile /env /user:mydomain\admin "mmc %windir%\system32\dsa.msc"
> runas /env /user:user@domain.microsoft.com "notepad \"my file.txt\""

NOTE:  Enter user's password only when prompted.
NOTE:  /profile is not compatible with /netonly.
NOTE:  /savecred is not compatible with /smartcard.



 DONE  Compiled successfully in 8472ms                                                                        3:21:46 pm


  App running at:
  - Local:   http://localhost:8080/
  - Network: http://172.16.11.112:8080/

  Note that the development build is not optimized.
  To create a production build, run npm run build.

```
## File stucture 

Package.json contains all the node package installed.
package.lock.json is lock file which contain detail info about the node modules.
.gitignore ignore the node module in the remote repository.
In public folder contains the html file which is loade dwhen apps run.
Firstly main.js is compiled and then vue file is compiled.

A app.vue structure is:
```
<template>
   html code
</template>
<script>
   js code
</script>
<style>
   css code
</style>
```

### day 2
## Component

Componenet can be search bar and header, about and footer etc. Mainly we can reuse the header components for all the pages.

I have Created a Home.vue file and create a component name HomeComp
```
<template>
    <h1>Home component</h1>
</template>
<script>
export default {
    name:'HomeComp',
}
</script>
```

And I have imported it in app.vue file as
```
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to code Step by Step"/>
  <HomeComp />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HomeComp from './components/Home.vue'
export default {
  name: 'App',
  components: {
      HelloWorld,
      HomeComp,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

```

Add some css and apply scope so that stype can be binded to a component and willm not affect stype of other component:
```
<template>
    <h1>Home component</h1>
</template>
<script>
export default {
    name:'HomeComp',
}
</script>

<style scoped>
    h1{
        color:red
    }
</style>
```

## Interpolation and Data
it helps to use js function and variable inside the vue components.
We can create function, Assign value to a variable. And we can assign value in thetemplate part of vue js 
```
<template>
    <h1>Home component {{10+10}}</h1>
    <h1>Home component {{"helllo".length}}</h1>
    <h1>Email:{{ email }}</h1>
    <h1>mobile:{{ mobile }}</h1>
    <h1>mobile:{{ mobile=88888 }}</h1>

    <h1>Name:{{ getName("Singh")}}</h1>


</template>
<script>
export default {
    name:'HomeComp',
    data(){

        return{
            email:'balsehra445@gmail.com',
            mobile:878767665,
            getName:function(a){
                return a;
            }
        }
    }
}
</script>

<style scoped>
    h1{
        color:red
    }
</style>
```
## Define and use method with parameter:
Data property is we use scripts tag to create function and and use function with this property and use method. also create amd use function multiple time.
```
<template>
    <h1>Home component {{10+10}}</h1>
    <h1>Email:{{ email }}</h1>
    <h1>Name :{{ getName("Peter") }}</h1>
    <h1>Name 2 :{{ getName("Stark") }}</h1>
    <h1>All data :{{ getData().email }}</h1>

</template>
<script>
export default {
    name:'HomeComp',
    data(){

        return{
            email:'balsehra445@gmail.com',
           
        }
    }, 
    methods:{
        getName(name){
            return name;
        },
        getData(){
            return {
                name: "baljit",
                email: this.email
            }
        }
    }
}
</script>

<style scoped>
    h1{
        color:red
    }
</style>
```

## Events in Vue js
Create a button and pass a function for the button. Learned on click, dbl click and mouse move parameters. And change data by clicking on button.
```
<template>
    <h1 v-on:mousemove="getConsole()">Home component {{10+10}}</h1>
    <button v-on:click="getData()">Click Me</button>
    <button v-on:dblclick="getData('Button Double clicked')">Click Me</button>
    <h2>{{count}}</h2>
</template>
<script>
export default {
    name:'HomeComp',
    data()
    {
        return{
            count:0
        }
    },
    methods:{
        getData()
        {
            this.count=this.count+1;
        },
        getConsole()
        {
            console.warn("function called")
        }
    }
    
}
</script>

<style scoped>
    h1{
        color:red
    }
</style>
```

## Two-way Binding in Vuejs
it saves complexity . it bind property with vue and model. model is js code in script tag and vue is in the template tag. We use v-model=count.
```
<template>
    <h1>Two way binding</h1>    
    <input type="text" v-model="count" />
    <h2>{{ count }}</h2>
</template>
<script>
export default {
    name:'HomeComp',
    data()
    {
        return {
            count:10
        }
    }
    
}
</script>

<style scoped>
    h1{
        color:red
    }
</style>
```
## Get input field value
Make 2 input field
Make function to get value
define data property 
apply two vay binding 
output is visible in console
```
<template>
<h1>Get input field value</h1>
<input type="text" placeholder="enter email" v-model="email" />
<br />
<br />
<input type="text" placeholder="enter password" v-model="password" />
<br />
<br />
<button v-on:click="getData()" type="button">Get Values</button>
</template>

<script>
export default {
    name: 'HomeComp',
    data()
    {
        return{
            email:null,
            password:null,
        }
    },
    methods:
    {
        getData(){
        console.warn("values:", this.email,this.password)
    }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Get checkbox and Radio Button value
Make checkbox and radio button with label. Print value of checkbox and Radio button values
```
<template>
<h1>Get CheckBox & Radio Button Value</h1>
<h3>Technology</h3>
<label for="c">C</label>
<input type="checkbox" value="c" id="c" v-model="technology" />

<label for="php">PHP</label>
<input type="checkbox" value="php" id="php" v-model="technology" />

<label for="node">Node</label>
<input type="checkbox" value="node" id="node"  v-model="technology" />
<h4> Selected Technology: {{ technology }}</h4>
<h4>I am a :{{ who }}</h4>

<br /> <br />
<h3>Who Am I</h3>
<label for="node">Student</label>
<input type="radio" value="student" name="who" id="student" v-model="who" />

<label for="node">Developer</label>
<input type="radio" value="developer" name="who" id="developer" v-model="who"  />


</template>

<script>
export default {
    name: 'HomeComp',
    data()
    {
        return{
            technology:[],
            who:null
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Conditional rendering(if-else)
Get value from html using conditions. Toggle if else using button
```
<template>
<h1 v-if="show">If Else Condition</h1>
<h1 v-else>Else Condition</h1>
<button v-on:click="show=!show" type="T">Toggle</button>

</template>

<script>
export default {
    name: 'HomeComp',
    data()
    {
        return{
            show:true
        }
    }


}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## For Loop in vuejs
Define array and apply loop and define array of object using for loop
```
<template>
<h1>For Loop in Vue js</h1>
<ul>
    <li v-for="item in technology" :key="item">
        {{ item }}

    </li>
</ul>
<br />
<br />
<ul>
    <li v-for="item in user" :key="item.email">
        Name is : {{ item.name }} and Email is : {{ item.email }}

    </li>
</ul>
</template>

<script>
export default {
    name: 'HomeComp',
    data() {
        return {
            technology: ['c', 'php', 'html', 'node'],
            user: [{
                    name: "Baljit",
                    email: "baljit@gmail.com"
                },
                {
                    name: "Aman",
                    email: "amant@gmail.com"
                },
                {
                    name: "Ram",
                    email: "ram@gmail.com"
                },
            ]
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Pass Data to Child Components
Make child component
Import and use child components
Pass Static Data
Pass Property object and function to child component
Created a new component in Child.vue
```
<template>
    <h2>{{name}}</h2>
    <h2>{{ user.name }}</h2>
    <button v-on:click="getData()">Call function</button>
</template>

<script>
export default{
    name: 'ChildNew',
    props:{
        name:String,
        user:Object,
        getData:Function
    }
}
</script>
```
And Home.vue is
```
<template>
    <h2>{{name}}</h2>
    <h2>{{ user.name }}</h2>
    <button v-on:click="getData()">Call function</button>
</template>

<script>
export default{
    name: 'ChildNew',
    props:{
        name:String,
        user:Object,
        getData:Function
    }
}
</script>
```
## Reuse Components
Make Child Component
Import and use Child components
apply for loop in array
Pass Property to child table

Created User.vue
```
<template>
<div class="user">
    <h2>{{ data.name }}</h2>
    <h2>{{ data.email }}</h2>
    <button v-on:click="getData(data.name)">Alert name</button>
</div>

</template>
<script>
export  default{
    name:'userNew',
    props:{
        data:Object,
        getData:Function
    },
}
</script>
<style>
.user{
    background-color: aquamarine;
    padding: 10px;
    border-bottom: 1px solid;
    margin-top: 20px;

}
</style>
```

and Home.vue is
```
<template>
<h1>Pass data to Child component</h1>
<ul>
    <li v-for="item in users" :key="item.name">
        <UserNew :data="item" :getData="getData" />
    </li>
</ul>

</template>

<script>
import UserNew from './User.vue'
export default {
    name: 'HomeComp',
    components: {
        UserNew
    },
    methods:{
        getData(name)
        {
            alert(name)
        }
    },
    data() {
        return {
            users: [{
                    name: "baljit",
                    email: "baljit@hma.com"
                },
                {
                    name: "Sam",
                    email: "samt@hma.com"
                },
                {
                    name: "bruce",
                    email: "bruce@hma.com"
                },
                {
                    name: "aman",
                    email: "aman@hma.com"
                }
            ]
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Html Binding
apply Html Binding and 2 html tag binding 
When we want to add dynamic data
```
<template>
<h1>{{ text }}</h1>
<div v-html="tag">
 </div>
<div v-html="tag2">

</div>
</template>

<script>
export default {
    name: 'HomeComp',
    data() {
        return {
            text: "baljit Singh",
            tag: "<h1>Baljit</h1>",
            tag2: "<h1>Baljit@gamil.com</h1>"

        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>
```

### Day 3

## Class Binding 
Add simple dynamic class. class came from js dynamically.
Change class on Button click
Dynamic class with functions
```
<template>
<h1>Class Binding</h1>
<h2 :class="applystyle">Home Component</h2>
<button v-on:click="colorfull=!colorfull">Apply Style</button>
</template>

<script>
export default {
    name: 'HomeComp',
    data() {
        return {
            colorfull: true
        }
    },
    computed: {
        applystyle() {
            return {

                green: this.colorfull,
                err: true,
                other: true

            }

        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}

.green {
    background-color: green;
    width: 150px;
    padding: 10px;
}

.err {
    color: red;
}

.other {
    font-size: 50px;
}
</style>

```

## Props
Props is when we want to tranfer data between two components is called props 
Data transfer in props
What can we pass on props
Home.vue is:
```
<template>
<h1>Props</h1>
<StudentNew :name="name" />
<TeacherNew name="Peter" />
</template>

<script>
import StudentNew from './Students.vue'
import TeacherNew from './Teacher.vue'

export default {
    name: 'HomeComp',
    components: {
        StudentNew,
        TeacherNew
    },
    data(){
        return{
            name: "bruce"
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>
```
Students.vue is:
```
<template>
<h2>Student Name is : {{ name }}</h2>
</template>

<script>
export default {
    name: 'StudentNew',
    props: {
        name: String
    }
}
</script>

```
Teacher.vue is:
```
<template>
    <h2>Teacher Name is: {{ name }}</h2>
    </template>
    <script>
    export default{
        name:'TeacherNew',
        props: {
        name: String
    }
    }
    </script>
```
## Send Clild Data to Parent Component
Make Clild Component. Inner componet is child
Pass data Function as Props
Share Clild Component with parent
Parent is home.vue:
```
<template>
<h1>{{ childuser }}</h1>
<UserNew :getUser="getuserName" />
</template>

<script>
import UserNew from './User.vue'

export default {
    name: 'HomeComp',
    data(){
        return{
            childuser:""
        }
    },
    components: {
        UserNew
    },
    methods: {
        getuserName(name) {
            this.childuser=name
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>
```
child is User.vue 
```
<template>
<h2>User Component</h2>
<button v-on:click="getUser(userName)" >Send User Name</button>
</template>

<script>
export default {
    name: "UserNew",
    data() {
        return {
            userName: "peter"
        }
    },
    props: {
        getUser:Function
    
    }
}
</script>
```
## Ref
Ref is used in react also. it is used to get/set/fetch form value 
Make input field and apply ref
Operations with ref
```
<template>
<h1>Ref in Vue js 3</h1>
<input type="text" ref="input" />
<button v-on:click="getData">Click Me</button>
</template>

<script>

export default {
    name: 'HomeComp',
    methods:{
        getData()
            {
            this.$refs.input.focus();
            let val=this.$refs.input.value;
            console.warn(val)
            this.$refs.input.style.color="red";
            }
        
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Simple form
Define some input field
apply two way binding
Print and Submit Value
```
<template>
<h1>Simple form</h1>
<p>
    {{ form }}
</p>
<form>
    <label>Email</label>
    <input type="text" placeholder="Enter Email" v-model="form.email" />
    <br />
    <br />
    <label>Password</label>
    <input type="password" placeholder="Enter Password" v-model="form.password" />
    <button type="button" v-on:click="login">Click Me</button>
</form>
</template>

<script>
export default {
    name: 'HomeComp',
    data()
    {
        return{
            form:{
                email:'',
                password:''
            }
        }
    },
    methods:{
        login()
        {
            console.warn("login data",this.form)
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Advance Form
Contine of last form
Add radio button, checkbox, Select box
Define Propert and bind value
Print and submit value
```
<template>
<h1>Simple form</h1>
<p>
    {{ form }}
</p>
<form>
    <label>Email</label>
    <input type="text" placeholder="Enter Email" v-model="form.email" />
    <br />
    <br />
    <label>Password</label>
    <input type="password" placeholder="Enter Password" v-model="form.password" />
    <br />
    <br />
    <select v-model="form.country">
        <option>India</option>
        <option>US</option>
        <option>China</option>
    </select>
    <br />
    <br />
    <h3>Technology</h3>
    <label>Html</label>
    <input type="checkbox" value="html" v-model="form.technology" />
    <br />
    <br />
    <label>Java</label>

    <input type="checkbox" value="java" v-model="form.technology" />
    <br />
    <br />
    <h3>Gender</h3>
    <label>Male</label>

    <input type="radio" value="male" name="gender" v-model="form.gender" />
    <label>Female</label>

    <input type="radio" value="female" name="gender" v-model="form.gender" />

    <button type="button" v-on:click="login">Click Me</button>
</form>
</template>

<script>
export default {
    name: 'HomeComp',
    data() {
        return {
            form: {
                email: '',
                password: '',
                country: '',
                technology: [],
                gender: ''
            }
        }
    },
    methods: {
        login() {
            console.warn("login data", this.form)
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>
```
## Form Validation
add error property
apply loop over form files and collect error
Use for loop to show error
```
<template>
<h1>Simple form</h1>
<ul>
    <li v-for="item in error" v-bind:key="item">
        {{ item }} not valid
    </li>
</ul>
<form>
    <label>Email</label>
    <input type="text" placeholder="Enter Email" v-model="form.email" />
    <br />
    <br />
    <label>Password</label>
    <input type="password" placeholder="Enter Password" v-model="form.password" />
    <br />
    <br />
    <select v-model="form.country">
        <option>India</option>
        <option>US</option>
        <option>China</option>
    </select>
    <br />
    <br />
    <h3>Technology</h3>
    <label>Html</label>
    <input type="checkbox" value="html" v-model="form.technology" />
    <br />
    <br />
    <label>Java</label>

    <input type="checkbox" value="java" v-model="form.technology" />
    <br />
    <br />
    <h3>Gender</h3>
    <label>Male</label>

    <input type="radio" value="male" name="gender" v-model="form.gender" />
    <label>Female</label>

    <input type="radio" value="female" name="gender" v-model="form.gender" />

    <button type="button" v-on:click="login">Click Me</button>
</form>
</template>

<script>
export default {
    name: 'HomeComp',
    data() {
        return {
            form: {
                email: '',
                password: '',
                country: '',
                technology: [],
                gender: ''
            },
            error: [],
        }
    },
    methods: {
        login() {
            this.error = [];
            for (const item in this.form) {
                if (this.form[item] == "" || this.form[item].length === 0) {
                    this.error.push(item)
                }
                if (this.error.length === 0) {
                    alert("error")
                }
            }
            console.warn("login data", this.form, this.error)
        }
    }

}
</script>

<style scoped>
h1 {
    color: red
}
</style>

```
## Modifiers
what is form modifiers and how to use modifiers.
