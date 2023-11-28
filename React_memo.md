## Creating and nesting components
React components are JavaScript functions that return markup.   E.g., 
```
function MyButton() {
  return (
    <button>I'm a button</button>
  );
} 
```
React component names must always start with a capital letter, while HTML tags must be lowercase.  
React component can be nested it into another component.  


## Writing markup with JSX
JSX is stricter than HTML. You have to close tags like <br/>.   
Your component also can’t return multiple JSX tags. You have to wrap them into a shared parent, like a <div>...</div> or an empty <>...</> wrapper.    
JSX lets you put markup into JavaScript.  
Curly braces let you “escape back” into JavaScript so that you can embed some variable from your code and display it to the user.  


## Rendering lists
Use the map() function to transform an array of products into an array of <li> items.  