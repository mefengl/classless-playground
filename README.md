# classless-playground

Run below in the browser's devtool's console to try it.

```js
(function() {
  const cssDetails = {
    new: {
      instruction: '<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@exampledev/new.css@1/new.min.css">',
    },
    sakura: {
      instruction: '<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sakura.css/css/sakura.css">',
    },
    matcha: {
      instruction: '<link rel="stylesheet" href="https://matcha.mizu.sh/matcha.css">',
    },
    bamboo: {
      instruction: '<link rel="stylesheet" href="https://unpkg.com/bamboo.css">',
    }
  };

  function showCode(cssType) {
    const displayArea = document.getElementById('css-instruction');
    displayArea.innerText = cssDetails[cssType].instruction;
  }

  function createButton(id, text) {
    const button = document.createElement('button');
    button.id = id;
    button.innerText = text;
    button.style.margin = '5px';
    button.style.padding = '10px';
    button.style.fontSize = '16px';
    button.addEventListener('click', () => showCode(id));
    return button;
  }

  // Create container for buttons
  const container = document.createElement('div');
  container.style.position = 'fixed';
  container.style.top = '10px';
  container.style.left = '10px';
  container.style.zIndex = '10000';
  container.style.backgroundColor = 'white';
  container.style.color = 'black';
  container.style.border = '1px solid black';
  container.style.padding = '10px';
  container.style.boxShadow = '0px 0px 10px rgba(0, 0, 0, 0.1)';
  container.style.maxWidth = '450px';

  // Create and append buttons
  container.appendChild(createButton('new', 'new.css'));
  container.appendChild(createButton('sakura', 'sakura.css'));
  container.appendChild(createButton('matcha', 'matcha.css'));
  container.appendChild(createButton('bamboo', 'bamboo.css'));

  // Create and append display area
  const displayArea = document.createElement('div');
  displayArea.id = 'css-instruction';
  displayArea.style.marginTop = '10px';
  displayArea.style.padding = '10px';
  displayArea.style.fontSize = '14px';
  displayArea.style.borderTop = '1px solid black';
  displayArea.style.color = 'black';
  displayArea.style.maxHeight = '100px';
  displayArea.style.overflowY = 'auto';
  displayArea.innerHTML = 'No CSS applied';
  container.appendChild(displayArea);

  document.body.appendChild(container);
})();
```
