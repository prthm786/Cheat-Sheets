# jQuery Notes 

jQuery is a JavaScript library designed to simplify HTML 
DOM tree traversal and manipulation, and event handling, 
CSS animation, and Ajax.


jQuery's syntax is designed to make it easier to navigate
a document, select DOM elements, create animations, handle events, 
and develop Ajax applications. jQuery also provides capabilities for 
developers to create plug-ins on top of the JavaScript library. 


```javascript
$(document).ready(function(){
  $("button").click(function(){
    $(this).hide();
  });
});
```

```javascript 
$(document).ready(function() {
  // code...
});
// Similar to DOMContentLoaded 

// This is to prevent any jQuery code from running before the document is finished loading (is ready).

// It is good practice to wait for the document to be fully loaded and ready before working with it. 
```

**JQuery features**
---
1. DOM Manipulation
2. DOM Traversing 
3. AJAX
4. Event Handling 
5. Animation


**jQuery Chaining**
```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("#p1").css("color", "red").slideUp(2000).slideDown(2000);
  });
});
```
---


## 1. DOM Manipulation
---

### Adding Elements 

- **.after()**
```javascript
$("button").click(function(){
  $("p").after("<p>Hello world!</p>");
});
$(document).ready(function(){
  $("button").click(function(){
    $("p").after(function(n){
      return "<div>The p element above has index " + n + ".</div>";
    });
  });
});
```

- **.before()**
`$(selector).before(content, 
function(index))`

- **.insertAfter()**

- **.insertBefore()**

- **.append()**

- **.prepend()**

- **​.appendTo()**

- **.prependTo()**
```javascript
$("button").click(function(){
  $("<span>Hello!</span>").prependTo("p");
});
```

### Attributes
- **.attr()** -> Sets or returns attributes/values of selected elements
- $(selector).attr(attr) -> Return value of attribute
- $(selector).attr(attr,value) -> Set the attribute value
- $(selector).attr(attr, function(index,currentVal) -> Set attribute value using a function

- **.removeAttr()**


### Properties
- .prop() -> Sets or returns properties/values of selected elements
.removeProp()
- .css() ->  add css 


### Class 
- **.hasClassss()**
- **.addClass()**
- **.toggleclass()**
- **.removeClass()**


### Get Content 
- **.html()** -> sets or returns the content of selected elements

- **.text()** -> sets or returns the text content of selected elements
$(selector).text() // Return text content
$(selector).text(content) // Set text content
$(selector).text(function(index, currentcontent)) 
// Set text content using a function.

- **.val()** -> sets or returns the value attribute of the selected elements (for form elements)

- **.position()** -> returns the position (relative to the parent element) of an element


### Replacing Elements
- **.replaceAll()**
- **.replaceWithith()**


**​.clone()**
$(selector).clone(true|false)


### Elements 
- **​.remove()** -> Removes the selected  elements (including data and events)
​- **.detach()** ->  Removes selected elements (keeps data and events)
- **​.empty()** -> Removes all child nodes and content from selected elements


### Wraping 
- **​.wrap()** -> Wraps HTML element(s) around each selected element
```javascript 
$(document).ready(function(){
  $("button").click(function(){
    $("p").wrap("<div></div>");
  });
});
```

- **​.wrapAll()** -> Wraps HTML element(s) around all selected elements at once 

- ​**.wrapInner()** -> Wraps HTML element(s) around the content of each selected element
$("button").click(function(){
  $("p").wrapInner("<b></b>");
});

- **.unwrap()** -> Removes the parent element of the selected elements
$(document).ready(function(){
  $("button").click(function(){
    $("p").unwrap();
  });
});

---
---

<br>
<br>


## 2. DOM Traversing
--

- **.children()**
- **.parent()** ->  parent 
- **.parents()** -> all ancestors 
- ​**.closest()** -> Returns the first ancestor of the selected element
- **​.contents()** -> Returns all direct children of the selected element (including text and comment nodes)
- **.prev()** -> previous sibling
- **​.next()** -> next sibling 
- **.prevAll()** ->  previous siblings
- **​.nextAll()** -> all next siblings
- **.siblings()** -> all siblings
- **​.first()** -> Returns the first element of the selected elements
​- **.last()** -> Returns the last element of the selected elements
- **​.find()** -> Returns descendant elements of the selected element

.is() // return true if at least one of these elements matches the given arguments
$(document).ready(function(){
  $("p").click(function(){
    if ($(this).is("p")) {
      alert("Parent of p is div"); 
    }
  });

.has() // all elements with one or more elements inside of them
$(document).ready(function(){
  $("p").has("span").css("color", "yellow");
});

.not() // Returns elements that do not match  certain criteria
​.filter() // Reduce the set of matched elements to those that match the selector or pass the function's test
$(document).ready(function(){
  $("p").filter(":not(.intro)").css("color", "yellow");
});

.each() // runs a function for each matched element
$(document).ready(function(){
  $("button").click(function(){
    $("ul").children().each(function(){
      alert($(this).text())
    });
  });
});

$("button").click(function(){
  $("up > li").each(function(){
    alert($(this).text())
  });
});

.eq() // Returns an element with a specific index number of the selected elements
$("p").eq(1).css("color", "yellow");
.lt()
.gt()

---
---

<br>
<br>


## 3. AJAX
---

​$.ajax() // runs an async AJAX request
url: "" 
type  //  ( GET | POST)
success(result,status,xhx) // function to run when req succeeds
error(xhr,status,error)	 // function to run if req fails.
dataType	// data type expected of the server 
contentType // type used for sending data to the server. Default is: "application/x-www-form-urlencoded"
complete(xhr,status)	//  run when the req is finished (after success , error functions)
beforeSend(xhr)	 // function to run before the req is sent
Async // true | false 
​data	// data to be sent to the server
​username // HTTP access authentication req 
​password // HTTP access authentication req
​xhr	// func used for creating the XMLHttpRequ

$(document).ready(function(){
  $("button").click(function(){
    $.ajax({url: "test.txt", success: function(result){
      $("#div1").html(result);
    }});
  });
});

$.get() // Loads data from a server using an AJAX HTTP GET request
$.get(URL , data , function(data,status,xhr) , dataType)
$("button").click(function(){
  $.get("test.asp", function(data, status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});

$.post() // Loads data from a server using an AJAX HTTP POST request
$(selector).post( URL , data , function(data , status , xhr) , dataType)
$("button").click(function(){
  $.post("test.asp", function(data, status){
    alert("Data: " + data + "\nStatus: " + status);
  });
});

.load() // Loads data from a server and puts the returned data into the selected element
$(selector).load( url , data , function(response , status , xhr)
$("button").click(function(){
  $("#div1").load("test.txt");
});
 
$.getScript() // Loads (and executes) a JavaScript from a server using an AJAX HTTP GET request
$(selector).getScript( url, success(response , status))
$(document).ready(function(){
  $("button").click(function(){
    $.getScript("ajax_script.js");
  });
});

$.getJSON() // Loads JSON-encoded data from a server using a HTTP GET request
$(selector).getJSON(url , data , success(data , status , xhr) )
$("button").click(function(){
  $.getJSON("ajax_json.js", function(res){
    $.each(res, function(i, field){
      $("div").append(field + " ");
    });
  });
});

.ajaxSuccess() // Specifies a function to run when an AJAX request completes successfully
$(document).ajaxSuccess( function( event , xhr , options))
$(document).ready(function(){
  $(document).ajaxSuccess(function(){
    alert("AJAX request successfully completed");
  });
  $("button").click(function(){
    $("div").load("ajax_load.txt");
  });
});

.ajaxError()
$(document).ajaxError( function( event , xhr , options , exc) )

.ajaxStart() // Specifies a function to run when the first AJAX request begins
$(document).ajaxStart(function() {})

.ajaxStop() // Specifies a function to run when all AJAX requests have completed
$(document).ajaxStop(function() {})

.ajaxComplete() // Specifies a function to run when the AJAX request completes
$(document).ajaxComplete(function( event , xhr , options))

.ajaxSend() // Specifies a function to run before the AJAX request is sent


.toArray() 
$("button").click(function(){
  var x = $("li").toArray()
  for (i = 0; i < x.length; i++) {
    alert(x[i].innerHTML);
  }
---
---

<br>
<br>

## 4. Events Handling
---

Can attach events to all the elements returned by the jQuery selector unlike the vanilla javascript querySelectorAll() which require the event to be attached to elements individually.

- **.click()**
```javascript
$(document).ready(function(){
  $("p").click(function(){
    alert("The paragraph was clicked.");
  });
});
//            OR 
$(document).ready(function(){ 
  $("p").each(function(){     
     $(this).click(function(){
            alert("Hello");
     })
  })
});
```

- **.dblclick()**
$(document).ready(function(){
  $("p").dblclick(function(){
    alert("The paragraph was double-clicked.");
  });
});

- **.keydown()**

- **.scroll()**
``` javascript
let x = 0;
$(document).ready(function(){
  $("div").scroll(function(){
    $("span").text( x+= 1);
  });
});
```

- **.focus()** & **.blur()**
```javascript
$(document).ready(function(){
  $("input").focus(function(){
    $(this).css("background-color", "yellow");
  });
  $("input").blur(function(){
    $(this).css("background-color", "green");
  });
});
```

- **.on()** -> Attaches event handlers to elements
```javascriot
$(document).ready(function(){
  $("p").on("click", function(){
    alert("The paragraph was clicked.");
  });
});
```

`event.type`
`​event.target`
`event.target === this`
`event.currentTarget`

`event.stopImmediatePropagation()`
`​event.isImmediatePropagationStopped()`

`​event.isPropagationStopped()`
`event.stopPropagation()`

The event.stopPropagation() method stops the bubbling of an event to parent elements, preventing any parent event handlers from being executed.

`event.preventDefault()`
`event.isDefaultPrevented()`
---
---

<br>
<br>


## 5. Animation
---
 
- **.animate()**
`$(selector).animate( {styles} , speed , easing , callback)
Speed 
milliseconds (like 100, 1000, 5000, etc)
"slow"
"fast"
`
```javascript
$(document).ready(function(){
  $("button").click(function(){
    var div = $("div");
    div.animate({height: 300}, "slow");
    div.animate({width: 300}, "slow");
    div.animate({height: 100}, "slow");
    div.animate({width: 100}, "slow");

    $("span").text(div.queue());   
  });
});
```

- **.delay()**
`$(selector).delay(speed,queueName)`
```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").delay("slow").fadeIn();
    $("#div2").delay("fast").fadeIn();
    $("#div4").delay(2000).fadeIn();
    $("#div5").delay(4000).fadeIn();
  });
});
```

- **.fadeIn()** & **.fadeout()**
```javascript
 $(document).ready(function(){
  $(".btn1").click(function(){
    $("p").fadeOut();
  });
  $(".btn2").click(function(){
    $("p").fadeIn();
  });
});
```

- **fadeToggle()** -> Toggles b/w the fadeIn() and fadeOut() 
`$(selector).fadeToggle(speed, easing, 
callback)`
```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").fadeToggle();
    $("#div2").fadeToggle("slow");
    $("#div3").fadeToggle(3000);
  });
});
```

- **.hide()** & **.show()**
```javascript
$(document).ready(function(){
  $(".btn1").click(function(){
    $("p").hide();
  });
  $(".btn2").click(function(){
    $("p").show();
  });
});
```

- **.toggle()** -> Toggles b/w the hide() and show() methods
`$(selector).toggle(speed, easing, 
callback)`
```javascript
$(document).ready(function(){
  $("button").click(function(){
    $("p").toggle();
  });
});
```

- **.slideUp()** -> (hides) the selected elements
```javascript
$(document).ready(function(){
  $(".btn1").click(function(){
    $("p").slideUp();
  });
  $(".btn2").click(function(){
    $("p").slideDown();
  });
});
``` 
---
---

<!-- - **.slideToggle-down (shows) the selected elements -->

<!-- .slideToggle()	// toggles b/w the slideUp() and slideDo -->
