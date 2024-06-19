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
JSX is stricter than HTML. You have to close tags like \<br/>.   
Your component also can’t return multiple JSX tags. You have to wrap them into a shared parent, like a \<div>...\</div> or an empty \<>...\</> wrapper.    
JSX lets you put markup into JavaScript.  
Curly braces let you “escape back” into JavaScript so that you can embed some variable from your code and display it to the user.  


## Rendering lists
Use the map() function to transform an array of products into an array of \<li> items.  

## Updating the screen (count the number of times a button is clicked)
import { useState } from 'react';
```
function MyButton() {
  const [count, setCount] = useState(0);
  // ...
}
```
[something, setSomething] = useState(initial number), first value of the bracket indicates the current state, and you van change state by calling setCount().  
If you render the same component multiple times, each will get its own state. Click each button separately.  

## Using Hooks
Functions starting with use are called Hooks. useState is a built-in Hook provided by React.  
You can only call Hooks at the top of your components (or other Hooks).  

## Export
**命名導出（Named Export）**  
命名導出允許你在一個文件中導出多個變量或函數，每個導出都有自己的名字。  
export const component = () => {}  
import { AllRoutes } from './path/to/AllRoutes';  
**默認導出（Default Export）**  
默認導出允許你在一個文件中導出一個主要的變量或函數。當導入這個默認導出的變量或函數時，可以給它任何名字。  
const component = () => {} ....... export default component  
import CommonLayout from './path/to/CommonLayout';  
**小結**
命名導出 用於導出多個變量或函數，導入時使用花括號。  
默認導出 用於導出單個主要變量或函數，導入時可以使用任意名稱且不需要大括號。  

## Navigation components
**Link 組件：** 生成一個實際的超連結（HTML <a> 標籤），用戶點擊連結後進行導航，適用於聲明式導航  
例如：`<Link to="/path">Link Text</Link>`  
**Navigate 組件：** 不生成任何可見的 HTML 元素，立即重定向用戶到指定路徑，適用於需要自動重定向的場景  
例如：`<Navigate to="/path" replace />`   
