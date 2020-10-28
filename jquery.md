## JQuery

### Initialiseren

```
<head>
   <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
</head>
```

### $document.ready()
```
// A $( document ).ready() block.
$( document ).ready(function() {
    console.log( "ready!" );
});
```
### button.onclick
```
$(input type=button).on('click', function() {
  console.log('clicked');
});
```
### uuidv4()
```
function uuidv4() {
  return ([1e7]+1e3+4e3+8e3+1e11).replace(/[018]/g, c =>
    (c ^ crypto.getRandomValues(new Uint8Array(1))[0] & 15 >> c / 4).toString(16)
  )
}
```


