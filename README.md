# Theme toggle
## Dependencies
vscode live sass compiler

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).



### Check for broswer support

```

<!DOCTYPE html>
<html>
<body>

<div id="result"></div>

<script>
// Check browser support
if (typeof(Storage) !== "undefined") {
    // Store
    localStorage.setItem("list", "<h1>John<h1>");
    appendToStorage("list", "<h2>David<h2>");

    // Retrieve
    document.getElementById("result").innerHTML = localStorage.getItem("list");
} else {
    document.getElementById("result").innerHTML = "Sorry, your browser does not support Web Storage...";
}

function appendToStorage(name, data){
    var old = localStorage.getItem(name);
    if(old === null) old = "";
    localStorage.setItem(name, old + data);
}
</script>

</body>
</html>

```
