# React Router:

<li><Link to="/">Home</Link></li>

Each Route yesterday was it's own mini App. Mouted/ unMouted. each component had their own ecosystem.

terminal:

````
create-react-app route-props-router

````

In previous examples:

````
< Route path="/something" component={Home} />]

or

< Route path="/something" render={() => { ..(code you put)... }) } />

````

Another way to use the **Render** Prop:

in App.js:

````

<ul>
<li><Link to="/">Home</Link></li>
<li><Link to="/users">Users</Link></li>

</ul>

<Route exact path="/" render={() =>{
return <h1>Home</h1>
}}/>

<Route exact path="/users" render={() =>{
return <h1>Users</h1>
}}/>

````

now you can do this:

````

<Route exact path="/users" render={() =>{
return <Home something="boom" />
}}/>

````

In your state object:

````
class App extends component{
	state ={
		users:[{name: "Phillipe"}, {name: "Mike"}]
	}
}

<Route exact path="/users" render={() =>{
return <Users users={this.state.users} />
}}/>

````

if I need to pass custom props and access to all the router stuff
available in arrow function

````
<Route exact path="/users/:index" render={(routeProps) =>{
const { users } = this.state
const user = users[routeProps.match.params.index]
return <h1>{user.name}</h1>
}}/>

````