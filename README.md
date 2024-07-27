# LocalStorage_and_EventDelegation

This is a 30-days javascript grinding  
js30 [https://github.com/ningh98/js30]  
15. LocalStorage_and_EventDelegation [https://github.com/ningh98/LocalStorage_and_EventDelegation]

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)



## Overview

This HTML and JavaScript code demonstrates how to create a simple to-do list application that stores its data in the browser's localStorage. The application allows users to add items to a list, mark them as done, and persist this data across page reloads.

### Screenshot

![](./screenshot.png)


### Links

- Live Site URL: [https://ningh98.github.io/LocalStorage_and_EventDelegation/]

## My process

### Built with

- HTML
- CSS
- Javascript



### What I learned



```js

function populateList(plates = [], platesList){
    platesList.innerHTML = plates.map((plate, i) => {
      return `
        <li>
          <input type="checkbox" data-index=${i} id="item${i}" ${plate.done ? 'checked' : ''}/>
          <label for="item${i}">${plate.text}</label>
        </li>
      `
    }).join('')
  }

  function toggleDone(e) {
    if(!e.target.matches('input')) return  // skip this unless it's an input
    const el = e.target
    const index = el.dataset.index
    items[index].done = !items[index].done
    localStorage.setItem('items', JSON.stringify(items))
    populateList(items, itemsList)
  }

  addItems.addEventListener('submit', addItem)
  itemsList.addEventListener('click', toggleDone)
  populateList(items, itemsList)
```



