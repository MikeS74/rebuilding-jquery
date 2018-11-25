## Rebuilding jQuery

A collection of code snippets and helpful tips to use vanilla JavaScript and CSS animations instead of jQuery.

---

- __[microjs.com](http://microjs.com/)__ - Micro JS libraries like AJAX and JSON
- __[youmightnotneedjquery.com](http://youmightnotneedjquery.com/)__ - Lots of helpful jQuery code snippet replacements (Set to IE 10)
- __[animate.css](https://daneden.github.io/animate.css/)__ - Simple yet effective CSS animations

---

## Code

Main AJAX function
```
function ajax(method, url, data, cb) {
  var xhr = new XMLHttpRequest();
  xhr.open(url, method, true);
  xhr.setRequestHeader("Content-type", "application/json; charset=utf-8");
  xhr.setRequestHeader("Accept", "application/json");
  xhr.onreadystatechange = function () {
    if (xhr.readyState === 4 && xhr.status === 200) {
      cb(JSON.parse(xhr.responseText));
    }
  }
  if (data) {
    xhr.send(JSON.stringify(data));
  } else {
    xhr.send();
  }
}
```
DOM Manipulation
```
var $ = document.querySelectorAll;
```
Changing Elements
```
parent.appendChild(el);
el.classList.add(className);

el.parentNode.removeChild(el);
el.classList.remove(className);
```
Modifying content
```
el.innerHTML = '___';
el.textContent = '___';
```
Event listeners
```
var click = function (el, fn) {
  el.addEventListener('click', fn);
}

var a = document.getElementById('___');
click(a, function () {
  alert('you clicked ___');
});
```

