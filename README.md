# ⚡ JS SOURCE

## 🔥 clickutils.js
### 💧 last version 1.0.3
### 💧 description
> * To prevent MITB from executing scripted click events, a clickutils.js has been developed. 
> * This script utilizes event listeners such as mousedown, mouseup, touchstart, and touchend.

> ### Note (repeated multiple times):
> All functions returned by clickutils are intended for a single use. Therefore, functions returned by clickutils should be re-added internally at the appropriate moment to avoid being executed only once.

### 💧 Quick setup
```html
<!--set to body-->
<script src="https://lib.duckode.com/js/clickutils.min.js"></script>
<script>
    const element = document.querySelector('.your-target-class');
    var canLoop = true; // Default: true
    const click = clickutils.click(element, 0, elementClick, canLoop);
    function elementClick(e) {
        // TODO: click action
        // parameter 'e': mouseup event
        console.log("element is click");
        click.removeLoop(); // to remove the loop can call this function
    }
</script>
```

### 💧 setup
```html
<script src="https://lib.duckode.com/js/clickutils.min.js"></script>
```

### 💧 function
> ### nClick & nTouch return by Promise
> * clickutils.click(element, button, func)
> * clickutils.nClick(element, button)
> * clickutils.touch(element, func)
> * clickutils.nTouch(element)

### parameter
> * element : any —— target element
> * button : number —— 0: left mouse button, 1: right mouse button
> * func : function —— action to add to


## 🔥 contextmenuutils.js
### 💧 last version 1.0.1
### 💧 description
> * Easy to add menu or list with javascript

### 💧 Quick setup
```html
<!--set to header-->
<link rel="stylesheet" href="https://lib.duckode.com/css/contextmenuutils.css">

<!--set to body-->
<script src="https://lib.duckode.com/js/contextmenuutils.min.js"></script>
<script>
    var toClickPoint = true; // Default: false
    document.addEventListener("click", (e) => {
        contextmenuutils.init(document.body, (b, c) => {
            c.style.paddingTop = '3px';
            c.style.paddingBottom = '3px';
        }, true);
        const changeColor = (item, callback) => {
            item.addEventListener("click", callback);
            item.addEventListener("mouseenter", () => {
                item.style.background = "#505050";
            });
            item.addEventListener("mouseleave", () => {
                item.style.background = "";
            });
        }
        contextmenuutils.addItem('Item 1', (item) => {
            changeColor(item, () => {
                // TODO: click item action
                console.log('item action 1');
            });
        });
        contextmenuutils.addItem('Item 2', (item) => {
            changeColor(item, () => {
                // TODO: click item action
                console.log('item action 2');
            });
        });
    });
</script>
```

### 💧 setup
```html
<link rel="stylesheet" href="https://lib.duckode.com/css/contextmenuutils.css">
<script src="https://lib.duckode.com/js/contextmenuutils.min.js"></script>
```

### 💧 function
> * contextmenuutils.init(p, fc)
> * contextmenuutils.addItem(t, fc)
> * contextmenuutils.remove()

### 💧 parameter
> * p : element —— parent of contextmenu
> * t : string —— item name
> * fc : function —— action to add to
> * b : element —— cover item element
> * c : element —— item element