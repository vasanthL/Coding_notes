# Javascript Tutorial

## Js Variables


```javascript
var num1=2,num3='krish',num4=40.0,num5=[1,2,3,4,5],num6={name:'vasanth',age:10,dept:'ece'}
console.log(num1,num3,num4,num5[2],num6,num6.name)
console.clear()
```

    2 krish 40 3 { name: 'vasanth', age: 10, dept: 'ece' } vasanth
    


```javascript
// JavaScript Variables
// name cannot start with digit but with (_ & $)
var $name=1,_name=2,name=3
console.log($name,_name,name)

```

    1 2 3
    


```javascript
// Numbers 
console.log(typeof(num1))
```

    number
    


```javascript
console.log(typeof(num6))
```

    object
    


```javascript
var a=2,b=5,c
c=a+b
console.log(c)
var diff = b-a
var mul = b*a
var div = b/a
console.log(c,diff,mul,div)
```

    7
    7 3 10 2.5
    


```javascript
console.log(typeof(1/0),1/0) // 1/0 returns infinity
console.log(typeof(15*'A'),15*'A') //  return NaN not applicable number both are numbers
```

    number Infinity
    number NaN
    

## In-Built Number Functions


```javascript
// toString()
var num1=10,num2=20.3
console.log(num2.toString(),typeof(num2.toString())) // to convert num to String
```

    20.3 string
    


```javascript
//parseInt(),parseFloat()
var str1='10.0',str2='20.3',str3=[1,2,3],str4='vasi'
console.log(parseInt(str1),typeof(parseInt(str1)))
console.log(parseInt(str2),typeof(parseInt(str2)))
console.log(parseInt(str3),typeof(parseInt(str3)))
console.log(parseInt(str4),typeof(parseInt(str4)))
```

    10 number
    20 number
    1 number
    NaN number
    


```javascript
console.log(parseFloat(str1),typeof(parseFloat(str1)))
console.log(parseFloat(str2),typeof(parseFloat(str2)))
console.log(parseFloat(str3),typeof(parseFloat(str3)))
console.log(parseFloat(str4),typeof(parseFloat(str4)))
```

    10 number
    20.3 number
    1 number
    NaN number
    


```javascript
console.log(8.4354.toFixed())
```

    8
    


```javascript
var num=45.234323
```


```javascript
console.log(num.toFixed(4))
```

    45.2343
    


```javascript
console.log(num.toFixed(2))
```

    45.23
    

## String Functions


```javascript
var str1='i love javascripy'
var str2='this is " javascript" working'
console.log(str1,'\n',str2)
```

    i love javascripy 
     this is " javascript" working
    


```javascript
//str.length to find length
console.log('<---- str.length ---->')
console.log(str1.length)
console.log(str2.length)
console.log('\n')
//str.indexof(sub) to find start index of sub
console.log('<---- str.indexOf() ---->')
console.log(str1.indexOf('lo'))
console.log(str2.indexOf('wo'))
console.log('\n')
//str.lastIndexOf(sub) to find last index
console.log('<---- str.lastIndexOf() ---->')
console.log(str1.lastIndexOf('i'))
console.log(str2.lastIndexOf('n'))
console.log('\n')
//str.slice() to get range in the string
console.log('<---- str.slice() ---->')
console.log(str1.slice(2,9))
console.log(str2.slice(3,10))
console.log(str1.slice(4))
console.log(str1.slice(-10))
console.log('\n')
//str.substring(start,length) to find the sub
console.log('<---- str.substring() ---->')
console.log(str1.substring(0,2))
console.log('\n')
```

    <---- str.length ---->
    17
    29
    
    
    <---- str.indexOf() ---->
    2
    22
    
    
    <---- str.lastIndexOf() ---->
    14
    27
    
    
    <---- str.slice() ---->
    love ja
    s is " 
    ve javascripy
    javascripy
    
    
    <---- str.substring() ---->
    i 
    
    
    


```javascript
// String Functions
// str.toUpperCase(),str.toLowerCase()
// str1.()
var str4='vasi',str5='krish'
console.log(str4.toUpperCase(),str5.toLowerCase())
```

    VASI krish
    


```javascript
// str1.concat(str2)
console.log(str4.concat(str5.concat(' is ','doing ','good')))
console.log('the '.concat('name ','is ','vasanth'))
```

    vasikrish is doing good
    the name is vasanth
    


```javascript
//str1.trim() to remove extra spaces from both side of string
'  vasi     '.trim()

```




    'vasi'




```javascript
//str1.chatAt(index) to get the car at index
var chr='z',str6="vasi"
str6.charAt(1)=chr
console.log(str6)
```


    evalmachine.<anonymous>:3

    str6.charAt(1)=chr

    ^

    

    ReferenceError: Invalid left-hand side in assignment

        at evalmachine.<anonymous>:3:6

        at Script.runInThisContext (vm.js:120:18)

        at Object.runInThisContext (vm.js:309:38)

        at run ([eval]:1054:15)

        at onRunRequest ([eval]:888:18)

        at onMessage ([eval]:848:13)

        at process.emit (events.js:315:20)

        at emit (internal/child_process.js:876:12)

        at processTicksAndRejections (internal/process/task_queues.js:85:21)



```javascript
// str1.split() to split strings and return a list
console.log('this is alphabet'.split(' '))
```

    [ 'this', 'is', 'alphabet' ]
    

## Null and Defined Values 


```javascript
var mv
console.log((mv))
mva=null
console.log(mva)
```

    undefined
    null
    

## Conditional If-else


```javascript
var num7=1
if(num7>7)
    {
        console.log('higher')
    }
else if(num<5)    {
        console.log('lower')
    }

else
    {
        console.log('false')
    }
```

    false
    


```javascript
var va='1'
if(va==1)
    {
        console.log('first name')
    
    }
else
    {
        console.log('second name')
    }
```

    first name
    

## Conditional Switch


```javascript
var day='sun'

switch(day){
    case 'mon':
        console.log('Monday')
        break
    case 'tue':
        console.log('tuesday')
        break
    case 'wed':
        console.log('wednesday')
        break
    case 'thr':
        console.log('thursday')
        break
    case 'fri':
        console.log('friday')
        break
    case 'sat':
        console.log('saturday')
        break
    case 'sun':
        console.log('sunday')
        break
    default:
        console.log('invalid day')
}
```

    sunday
    


```javascript
// to find the operation
var num1=5,num2=3
var op='/'
switch(op)
    {
        case '+':
            console.log(num1+num2)
            break
        case '-':
            console.log(num1-num2)
            break
        case '*':
            console.log(num1*num2)
            break
        case '/':
            console.log((num1/num2).toFixed(2))
            break
        default:
            console.log('invalid operation')
    }
```

    1.67
    

## Arithmetic and Logical Operation


```javascript
// Arithemtic (=,-,*,/ (float),% (rem) ,// (quotient))
//Assignemnt (+=,-=,*=,/=)
//comparison(==,<=,!=,>=,===)
//logical (&& - and,|| - or,! - not )
//ternary operator
(2>1 && 5<7) ?console.log('crct') : console.log('wrong')
```

    crct
    


```javascript
('v'=='v'&&5!=2) ? console.log('one is correct') : console.log('both are wrong')
```

    one is correct
    

## Implicit and Explicit Type Conversion


```javascript
//implicit type conversion
var a=5,str1='hello',c='3',d=70.3
console.log(typeof(a),typeof(+c),typeof(c),typeof(d),d)
```

    number number string number 70.3
    


```javascript
if(0 || '' || null || undefined || NaN)
    {
        console.log(true)
    }
```


```javascript
// explicit type Conversion
var n1='3'
console.log(typeof(Number(n1)),typeof(Number('30.0')),30.000056)
```

    number number 30.000056
    

## Objects


```javascript
var obj1={
    name:'veryon',
    brand:'bugatti',
    top_speed:300,
    size:[31,22,45],
    specs:
    {
        torque:342.2,
        fuel:13.1,
        brakes:'disk'
    }
}

console.log(obj1.name,obj1.top_speed,obj1.size)
console.log(obj1.specs.torque,obj1.specs.brakes)
```

    veryon 300 [ 31, 22, 45 ]
    342.2 disk
    


```javascript
var envy={
    name : 'envy',
    brand : 'hp',
    size : 13.3,
    display:'ips',
    internal:{
        disk: 512,
        ram : 8,
        graphics :'gtx 1660',
    }
}
console.log(envy.name,envy.brand)
console.log(envy.internal.disk,envy.internal.ram,envy.internal.graphics)
```

    envy hp
    512 8 gtx 1660
    


```javascript
var phone={
    name:'note 10',
    brand: 'redmi',
    size: 6.5,
    display :'amoled',
    specs:{
    ram:'8gb',
    processor:'sd 855+',
    battery:'4500mah',
    storage:'128gb'
     },
    show_specs:function(){
        setTimeout(function(){
            console.log(phone.specs)
        },10000)
    }
 
}
phone.show_specs()
```

    {
      ram: '8gb',
      processor: 'sd 855+',
      battery: '4500mah',
      storage: '128gb'
    }
    


```javascript
//practicing objects and functions
var details={
    name:"vasanth L",
    age:22,
    height:5.72,
    langs:['c','c++','python','js'],
    marks:{
    maths:22,
    phys:25,
    csc:34
}
}
//console.log(details.name,details.langs,details.langs[2],details.marks.csc)
var func=function(){
    setTimeout(function(){console.log('hell world')},8000)
}
var int=function(){
    setInterval(function(){console.c},1000)
}
```

    hell world
    


```javascript
var scale={
    time:'8.46',
    show_time:function(){
        setTimeout(function(){
            console.log(scale.time)},5000
        )},
    clear_time:function(){
        setTimeout(function(){
            console.log('cleared')},2000
        )
    },
    show_spec:function(){
        setTimeout(function(){
        phone.show_specs()},1000
        )
    }
}
scale.show_time()
scale.clear_time()
scale.show_spec()
```

    {
      ram: '8gb',
      processor: 'sd 855+',
      battery: '4500mah',
      storage: '128gb'
    }
    cleared
    8.46
    


```javascript
// setTimeOut() to set the function to run after a time
// setInterval() to repeat the function after a specified time
var s=function(){setTimeout(function(){
    console.log('alert')
},2000
)}
s()
var r= function(){
    setTimeout(
        function(){
            console.log('hi')
        },1000
    )
}
r()

```

    hi
    alert
    


```javascript
var rd=function(){
    setTimeout(
        function(){
            console.log('working well :)')
        },2000
    )
}
rd()
```

    working well :)
    


```javascript
var start=1,loop=function(){
    setInterval(
        function(){
            console.clear()
            console.log(start)
            start+=1
        },1000
    )
}
```

    1
    2
    3
    


```javascript
var s=setTimeout(function()
                {
    console.log('hiii')
},1000)
s
```




    Timeout {
      _idleTimeout: 1000,
      _idlePrev: [TimersList],
      _idleNext: [TimersList],
      _idleStart: 95480,
      _onTimeout: [Function],
      _timerArgs: undefined,
      _repeat: null,
      _destroyed: false,
      [Symbol(refed)]: true,
      [Symbol(asyncId)]: 31,
      [Symbol(triggerId)]: 28
    }



    hiii
    


```javascript
var r=1
var t=function(){
    setInterval(
    function(){
        console.log('1')
    },100)
}

```

## Arrays


```javascript
var ls1=[1,2,3,4,5]
console.log(ls1[4])
//add new element to end of list
ls1[ls1.length]=6
ls1.push(7) // add value to last of the list
ls1.pop() // removes last element
ls1
```

    5
    




    [ 1, 2, 3, 4, 5, 6 ]



## Arrays Methods


```javascript
var mf=['sh','cl','vab','kun']
mf.splice(3,0,'do','rc')
mf.splice(2,0,'as','dc')
mf
```




    [
      'sh', 'cl',  'as',
      'dc', 'vab', 'do',
      'rc', 'kun'
    ]




```javascript
//ls.splice(start,ele to delete,elements to add from start)
mf.splice(2,0,'rd','yt')
mf
```




    [
      'sh', 'cl', 'rd',
      'yt', 'rd', 'yt',
      'rd', 'yt', 'vab',
      'do', 'rc', 'kun'
    ]




```javascript
//ls2.concat(ls2) - to concat list
mf.concat([1,23])
mf.concat(['zz','xz'])
```




    [
      'sh', 'cl',  'as',
      'dc', 'vab', 'do',
      'rc', 'kun', 'zz',
      'xz'
    ]




```javascript
//sorting a list (ls.sort())
console.log(mf.sort())
ls1=[33,5,12,78,24]
console.log(ls1.sort())
```

    [
      'cl', 'do', 'kun',
      'rc', 'rd', 'rd',
      'rd', 'sh', 'vab',
      'yt', 'yt', 'yt'
    ]
    [ 12, 24, 33, 5, 78 ]
    


```javascript
//reversing a list (ls.reverse())
console.log(ls1.reverse())
```

    [ 78, 5, 33, 24, 12 ]
    

# Loops

### While Loops


```javascript
var m=0
/*while(m<5){
    console.log(m)
    m+=1
}*/
while(m<25){
    if (m%3==0){
        console.log(m)
    }
    m+=1
}

```

    0
    3
    6
    9
    12
    15
    18
    21
    24
    




    25




```javascript
var ra=0
while (ra<6){
    console.log(ra)
    ra+=1
}
```

    0
    1
    2
    3
    4
    5
    




    6



### For Loops


```javascript
var n=[1,2,3,4,5],sq=[],pos=0
for(pos=0;pos<n.length;pos++){
    sq.push(n[pos]*n[pos])
    console.log(n[pos]," square is ",sq[pos])
}
sq
```

    1  square is  1
    2  square is  4
    3  square is  9
    4  square is  16
    5  square is  25
    




    [ 1, 4, 9, 16, 25 ]




```javascript
l=[1,2,3,4,5]
for(i=0;i<l.length;i++){
    if(l[i]==2){
        continue
    }
    if(l[i]==4)
        break
    console.log(l[i])
} 
```

    1
    3
    

## Functions


```javascript
/*
syntax [
function funcname(pm1,pm2,..pmn)
{

}

]*/
```


```javascript
var a=5,b=10
var c=function(){
    console.log('a=>',a)
    console.log('b=>',b)
    console.log('c=>',a+b)
}
c()
```

    a=> 5
    b=> 10
    c=> 15
    


```javascript
var a=3,b=8
function c(a,b){
    return('c=>',a+b)
}
c(2,3)
```




    5




```javascript
var name='welcome'
function greet(name){
    console.log('Welcome '+name+' :)')
}
greet('vasi')
function groo(name){
    console.log('he is a '+name+'dump')
}
```

    Welcome vasi :)
    


```javascript
ls=[22,33,1,1,1]
function prod(ls){
    var i,mul=1
    for(i=0;i<ls.length;i++)
        {
         mul*=ls[i]   
        }
    return mul
}
prod([23,4,5,663,2])
```




    609960



## Scope and Environment


```javascript
var name = 'vasi' // global scope
function gret(name){
    var name ='hell' // local scope
    console.log('welcome'+name)
}
greet('hello') // but this idiot gets executed 
```

    Welcome hello :)
    


```javascript
// JS sequence on scripts
 x='some'
 console.log(x) //willwork
 var x

```

    some
    


```javascript
sum(5,10) //this tooo works
function sum(a,b){
    console.log(a+b)
}
```

    15
    


```javascript
var sum=function(n1,n2){
    var total
    total=n1+n2
    console.log(total)
}
sum(29,14)
```

    43
    

# Document Object Model


```javascript
/*
  Tree representation f HTML
  When page is loaded,Browser creates dom
  DOM tree can be modified in JS
*/
/*
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>

</body>
<script>
    console.log("this is javascript")
</script>
</html>
*/

```


```javascript
// External javascript
/*
<!DOCTYPE html>
<html>
<head>
	<title></title>
    <script type='text/javascript' src='/index.js'></script>
</head>
<body>

</body>
</html>
*/
```

## Selecting HTML Elements


```javascript
// to get elements by id
//console.log(document.getElementById('id'))
//console.log(document.getElementsByClassName('class'))
//console.log(document.getElementsByTagName('TagName'))
//console.log(document.querySelector('#id .class'))
//console.log(document.querySelectorAll('#id .class'))
```


```javascript
/*console.log('script loaded')
console.log(document.getElementById('name'))
console.log(document.getElementById('color'))
console.log(document.getElementsByClassName('pure-button'))
console.log(document.getElementsByTagName('label'))
*/
```

### Query Selector


```javascript
// query selector will 2x slower than getelement method
/*
console.log(document.querySelector('.pure-button'))
console.log(document.querySelectorAll('#email'))
*/
```

## Updating HTML Content and Attributes


```javascript
//var init=count.innerHTML
 //image.src
/*
var count=document.getElementById('count')
console.log(count.innerHTML)
var init=count.innerHTML
var image=document.getElementById('imag')
var border=document.getElementsById('container1');
console.log(border)
var in_width=image.width
console.log(image)
function bgm(){
        count.innerHTML=(init>0)?init:0
        image.src=(init%2==0)?"image33.jpg":"image22.jpg"
        init-=1
        if(init<0)
{
	console.log(init)
	clearInterval(loop)
}
}

function wd(){
	count.innerHTML=(init>0)?init:0
        image.width=(in_width/100)*(init*10)
        init-=1
        if(init<0)
{
	console.log(init)
	clearInterval(loop)
}

}
*/
//var loop=setInterval( wd,1000)

```

## Set properties



```javascript
// setTimeout(function,timeinterval)
//setInterval(function,loop time)
//clearInterval(setInterval_variabel)
```

## Updating CSS Style Properties


```javascript
/*
  Syntax 
  var  ele=getElementById('selector')
  ele.style.{propertyname}=value;
  e.x.(selectedElement.style.width='300px')
*/
```

## Intro Into Events


```javascript
// types of events:
// mouse click,hover,key press,window load and resize ,form submission, video played

```


```javascript
/*syntax of event handling
var selectedelement=getElementById("Seelctor")/querySelector('Selector')

method1: Events Properties
syntax:selectedElement.{event.property}=function(){}
ex:selectedElement.onclick=function(){}

method2: add EventsListener()
syntax: selectedElement.addEventListener({eventName},function(){})
ex: selectedElement.addEventListener('click',function{})
*/
```


```javascript
/*name() automatically calls function
ex.ele.onclick=func1;
ex.ele.addEventListener('click',func1);
*/
```

## Add or Remove classes Using JavaScript


```javascript
/*
  classList holds all the classes of an HTML element
  ADD Class:
  we can use the method add()
  var selectedElement=getElementById('selector')/querySelector('selector')
Syntax: selectedElement.classList.add/remove('myclass');
e.x.:  selectedElement.classList.add/remove('show');
        selectedElement.classList.contains('show'); for list check
*/
```

## Getting Styles Using Javascript


```javascript
/*
<link rel="stylesheet" href="mystyle.css"> External CSS
<p style="color:blue; font-size:36px"></p>


var select=document.getElementById('selector')

INLINE STYLES:
select.style.width;

CSS FILE STYLES:
window.getComputedStyle(select).width (to get only value)
and styles can be changed manually select.style.width
*/
```

## Form Events


```javascript
/* change,focus,blur,submit 
change- when values changes
focus - input focused
blur - when input field loses focus
submit- when submit is pressed
input - to get input values

user.addEventListener('input',function(e){
    var name= e.target.value

    console.log(e.target.value)
    e.target.value=name.toUpperCase();
})

form.addEventListener('submit',function(e){
    alert('button submitted');
    e.preventDefault();
})

*/
```

## Keyboard Event


```javascript
/*
 three types of keyboard events:
 keypress  any press except shift,fn and cpslock
 keyup 
 keydown
 event.keycode to get the keycode value
 document.body.addEventListener('keypress',function(e){ console.log(e.keycode)})
 
 //sample code
 document.addEventListener('keydown',function(e){
    var keycode9=e.keyCode;
    console.log(keycode9);
    if(keycode9===76)
    {
        keyL.style.borderColor="red";
       keyLnote.play();
       setTimeout(function(){
           keyL.style.borderColor="black";
       },300)

    }
   }) 
   
 
*/
```

## Mouse Event


```javascript
/*
  these are the mouse events available:
  mousedown
  mouseup
  click
  dbclick
  mouseover
  mouseenter
  mouseover
  
  over.addEventListener('mouseover',function(){
    console.log('div1 mouse hovered')
    count1+=1
    hoverCount1.innerHTML=count1
})

*/
```

## Add Html Elements


```javascript
/*
    var element = document.createElement('li') -  to create an li element
    element.appendchild(document.createTextNode('vasi')) - to add vasi text to li value
    element.id='item2' - to add id to new element
    task.appendChild(element) - to add new li (element) to the ul -  task
    
    addItem.addEventListener('click',function(){
    var element= document.createElement('li')
    count+=1
    element.appendChild(document.createTextNode('list item '+count))
    element.id="item"+"count"
    element.className="item"
    tasks.insertBefore(element,tasks.firstElementChild)  // to insert element before the respective element
})
    
*/
```

## Updating Html Elements and Add Icons


```javascript
/*
 task.removeChild(task.firstElementChild) - to remove first Element Child
 task.replaceChild(newElementNode,task.firstElementChild) - to replace first Element with given Child
 
 font awesome - website to add icons to the html page
 <script src="https://kit.fontawesome.com/2360afe964.js" crossorigin="anonymous"></script> - to get icons
 
*/
```


```javascript
/*
JAVASCRIPT CODE FOR DELETE BUTTON

console.log('JS file is loaded')
var value=document.getElementById('value')
var addBtn=document.getElementById('add')
var updateBtn=document.getElementById('update')
var deleteBtn=document.getElementById('delete')
var task=document.getElementById('task')
var item="",count=0

const todoObjectList=[] //list of all objects

class todoList{
    constructor(item){
        this.ulElement=item
    }
    add()
    {
        if(value.value!==''){
        var todoInput=value.value
        var todoObject={
            id:todoObjectList.length,
            todoText:todoInput
        }
        todoObjectList.unshift(todoObject)
        this.display()
        value.value=''
        }
        else{ alert('Enter a value...')}

    }
    delete(x)
    {
       var delItem=todoObjectList.findIndex((item)=>item.id==x)
       todoObjectList.splice(delItem,1)
       this.display()

    }
    display()
    {
        this.ulElement.innerHTML=''
        todoObjectList.forEach((object)=>{
            var element=document.createElement('li')
            var delElement=document.createElement('i')
            element.innerText=object.todoText
            element.setAttribute('data-id', object.id)
            element.appendChild(document.createTextNode('\u00A0\u00A0\u00A0'))
            delElement.setAttribute('data-id',object.id)
            delElement.classList.add('fas','fa-trash')

            element.appendChild(delElement)

            element.addEventListener('click',function(){
                alert('element is clicked')
            })
        
            delElement.addEventListener('click',function(e){
                if(todoObjectList.length!==0){
                var event=e.target.getAttribute('data-id')
                myList.delete(event)
                }
                else{ alert('list is Empty...')}

            })

            this.ulElement.appendChild(element)
        })

    }
}

var myList=new todoList(task)

addBtn.addEventListener('click',function(){
    myList.add()
})


*/
```

## Browser Object Model


```javascript
//represents the current browser window
// types - document,history, location, screen, navigator
/*
 window.innerWidth ,innerHeight - to get the width and height of the screen


Window Object - setTimeout(), setInterval(), alert(), confirm(), prompt(), open(), close()

confirm - alert with yes or cancel
prompt - alert to get  a input value
open(link) - to open link in new tab
close()  - to close the current tab

*/
```

## Screen and Navigator Object



```javascript
/*

screen - to get all the screen parameters
screen.width,height - to get the full tab screen width
screen.availWidth,availHeight - to get the complete laptop screen width and height

------------------------------navigator object---------------------------------

navigator.userAgent - to get the info about a browser name and opersting sys type and etc
navigator.online - to get whether the user is online or not

*/
```

## History and Location Object


```javascript
/*
 window.history - to give the no of forward and back pages
 
 window.history.forward() - to move forward to the next page
  window.history.back() - to move backward
  
  -----------------------location----------------------------
   
  window.location.href - to get the url of the current page eg(www.google.com/index.html)
  window.location.hostname - to get the location of the hostname eg(www.google.com)
  window.location.pathname - get all after hostname eg(index.html)
  window.location.search - to get all values after ? eg(''?q=javascript')
  window.location.assign(link) - to open link in the same tab

*/
```

## Regular Expression


```javascript
// def - object that describes a pattern of characters, allows us to search for certain patterns of text
//ex( ) - to check whether the given string is valid email or not
// to check whether username contains only alpha and numbers

//syntax (/pattern-string/flag) pattern-string - string this pattern should match,
//forward slash - represents the start and end of the pattern
//flags - defines to search for case sensitive,insensitive , first result or all

```


```javascript
/* 
 website(regular expression 101) - to search for regular expression
 example('This is a black ball pen. This pen is really smooth. It is a parker PEN.') - test string
 
R.e. - /pen/m - for multiline
R.e. - /pen/mg - for multiline,global
R.e. - /pen/mgi - for multiline,global,insensitive

*/
```

## Meta Characters and Character Classes


```javascript
/*
    SET, RANGES AND CHARACTER CLASSES
    set,ranges - several char inside the sq bracket[...] eg[ABC] - any of the three char A,B,C can be matched -def(set)
    (ex : String: Air Birm Circle 
          Pattern: [ABC]irm)
    [] - may also contain char ranges eg - [A-Z] range(A to Z), [0-9] 0 to 9
    (ex : String: Same Name Fame Glam)
    Pattern: [A-Z]ame

    STRING - PATTERN
    vas0          [a-z][a-z][a-z][0-9]
    00v           [0-9][0-9][a-z]
    AVa           [A-z]
    spaces        [\s]
    symboles      [^A-z0-9\s]
    not           ^
    int          [\d]
    not int      [\D]
    char         [\w]
    not char     [\W]
*/
```

## Regex Quantifiers


```javascript
/*
    Quantifiers - select a value multiple times. Decides how many times a value is to be selected
    
    Sample String: He was born in the year 1990and His age is 29%@
    
    Syntax:    [\d]{3}   {3} quantifier to select 3 integers eg(19,90,29)
               [\d]{2-4} {2-4} select range 2,3,4    eg(1990,29) //234 is there is one like this
               [\d]{1,}   {1,}select range >1 eg(1,12,1,3323124) or else [\d]+
               ^,$        start, end characters
               ^#[a-fA-F0-9]{6}$  to select exact color codes eg(#23ef23) note: string should start with (#)
               ^[A-z]{5}[0-9]{4}[A-z]$  aaaaa9949q
               [0-9]*[\S]      1000 100 10 1 - to select a range of no without double spaces
               https{0,1} or https? to select both http and https

*/
```

## Using Regex Inside JavaScript


```javascript
/*
    Syntax: /{pattern}/{flag}
    or
    Syntax: new RegExp('pattern','flags')
    
    RegExp Methods:
        str.search(pattern) - returns the string position of the first match
        pattern.test(str) - true if there is a match else false
        str.match(pattern) - return the matched string if global returns an array of all strings
*/
```


```javascript
console.log('-----------------------------------Search Method----------------------------------------------------')
var str = 'this is a pen. this pen writes well, it is a parker pen'
var pattern = /pen/gi
console.log(str.search(pattern))
console.log('-------------------------------------test Method------------------------------------------------------')
var str = 'this is a pen. this pen writes well, it is a parker pen'
var pattern = /pen/
console.log(pattern.test(str))
console.log('-------------------------------------Match Method------------------------------------------------------')
var str = 'this is a pen. this pen writes well, it is a parker PEn'
var pattern = /pen/gi
console.log(str.match(pattern))
console.log('-------------------------------------Match Method------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = /[a-zA-Z]{3}[0-9]{2}/gi
console.log(str.match(pattern))
console.log('-------------------------------------Match Method------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = /[A-z]{1,}/gi
console.log(str.match(pattern))
console.log('-------------------------------------Match Method------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = /[\d]/gi
console.log(str.match(pattern))
console.log('-------------------------------------Match Method------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = /./gi   //to select all
console.log(str.match(pattern))
```

    -----------------------------------Search Method----------------------------------------------------
    10
    -------------------------------------test Method------------------------------------------------------
    true
    -------------------------------------Match Method------------------------------------------------------
    [ 'pen', 'pen', 'PEn' ]
    -------------------------------------Match Method------------------------------------------------------
    [ 'pen01' ]
    -------------------------------------Match Method------------------------------------------------------
    [
      'this',   'is',
      'a',      'pen',
      'this',   'pen',
      'writes', 'well',
      'it',     'is',
      'a',      'parker',
      'PEn'
    ]
    -------------------------------------Match Method------------------------------------------------------
    [ '0', '1' ]
    -------------------------------------Match Method------------------------------------------------------
    [
      't', 'h', 'i', 's', ' ', 'i', 's', ' ',
      'a', ' ', 'p', 'e', 'n', '0', '1', '.',
      ' ', 't', 'h', 'i', 's', ' ', 'p', 'e',
      'n', ' ', 'w', 'r', 'i', 't', 'e', 's',
      ' ', 'w', 'e', 'l', 'l', ',', ' ', 'i',
      't', ' ', 'i', 's', ' ', 'a', ' ', 'p',
      'a', 'r', 'k', 'e', 'r', ' ', 'P', 'E',
      'n'
    ]
    


```javascript
//Using RegExp class
console.log('-------------------------------------RegExp Class------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = new RegExp('pen','gi')
console.log(str.match(pattern))
console.log('-------------------------------------RegExp Class------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = new RegExp('[0-9]{2}','gi')
console.log(str.match(pattern))
console.log('-------------------------------------RegExp Class------------------------------------------------------')
var str = 'this is a pen01. this pen writes well, it is a parker PEn'
var pattern = new RegExp('[A-z]{3}[0-9]{2}','gi')
console.log(str.match(pattern))
```

    -------------------------------------RegExp Class------------------------------------------------------
    [ 'pen', 'pen', 'PEn' ]
    -------------------------------------RegExp Class------------------------------------------------------
    [ '01' ]
    -------------------------------------RegExp Class------------------------------------------------------
    [ 'pen01' ]
    

## RegExp Groups


```javascript
//() selecting a phone no
var str='9809809807'
var pattern=/^(\+91)?[\d]{10}$/gi
console.log(str.match(pattern))
```

    [ '9809809807' ]
    


```javascript
//() Selecting a phone no
var str='9809789788'
var pattern=new RegExp('^(\+91)?[0-9]{10}$','gi')
console.log(str.match(pattern))
```


    evalmachine.<anonymous>:3

    var pattern=new RegExp('^(\+91)?[0-9]{10}$','gi')

                ^

    

    SyntaxError: Invalid regular expression: /^(+91)?[0-9]{10}$/: Nothing to repeat

        at new RegExp (<anonymous>)

        at evalmachine.<anonymous>:3:13

        at Script.runInThisContext (vm.js:120:18)

        at Object.runInThisContext (vm.js:309:38)

        at run ([eval]:1054:15)

        at onRunRequest ([eval]:888:18)

        at onMessage ([eval]:848:13)

        at process.emit (events.js:315:20)

        at emit (internal/child_process.js:876:12)

        at processTicksAndRejections (internal/process/task_queues.js:85:21)



```javascript
// to fins the valid url
var str='www.facebook.in'
var pattern=/^www\.[\w]+\.(com|co|in|org)$/g
console.log(str.match(pattern))
```

    [ 'www.facebook.in' ]
    


```javascript
// to find a valid name
var str='www.facebook.co'
var pattern=/www\.[\w]+\.(com|co|ml|in|org)/g
console.log(str.match(pattern))
```

    [ 'www.facebook.co' ]
    

# Objects Oriented Programming JS



```javascript
var object={
    username:'vasi',
    password:2579,
    metric:'a1',
    getname:function(){
        return this.username
    },
     getpswd:function(){
        return this.password
    }
}

console.log(object.getpswd())
```

    2579
    

## This Keyword


```javascript
var object={
    username:'vasi',
    password:2579,
    metric:'a1',
    getname:function(){
        return this.username
    },
     getpswd:function(){
        return this.password
    },
    parent:{
    username:'loganathan',
    password:2345,
    getname:function(){
    return this.username
}
}
}

console.log(object.parent.getname())
```

    loganathan
    

## Constructor


```javascript
function person(fname,lname,dob){
    this.fname=fname
    this.lname=lname
    this.dob=dob
    this.getage=function(){
        console.log(2020-this.dob)
    }
}
var vasi=new person('vasanth','loganathan',1998)
console.log(vasi)
```

    person {
      fname: 'vasanth',
      lname: 'loganathan',
      dob: 1998,
      getage: [Function]
    }
    


```javascript
function mobile(processor,ram,battery){
    this.processor=processor
    this.ram=ram
    this.battery=battery
}
var m31s=new mobile('exynos 9611','8gb','7000mah')
var nord=new mobile('sd 756g','8gb','4500mah')
console.log(m31s,'\n',nord)
```

    mobile { processor: 'exynos 9611', ram: '8gb', battery: '7000mah' } 
     mobile { processor: 'sd 756g', ram: '8gb', battery: '4500mah' }
    

## Proto Function


```javascript
function detail(fname,dob){
    this.fname=fname
    this.dob=dob
}

detail.prototype.getage=function(){
    return this.age=(2020-this.dob)
}

detail.prototype.changedob=function(e){
         this.dob=e
}

var vasi=new detail('vasanth L',1998)

console.log(vasi.getage())

console.log(vasi.changedob(1999))
console.log(vasi.dob)
```

    22
    undefined
    1999
    

# HTTP Request


```javascript
// Understanding Frontend and Backend

/*
    front End                       BackEnd
    client side                     Server side   of an app
    includes all in screen          where data is handled sends and receives data
    html,css,js,react               nodejs,dotnet,php,java
    
*/
```


```javascript
// HTTP Methods

/*
GET - get data from bknd data type can be JSON object or JSON array
POST - creates new entries in bknd accepts some data in request and takes data to bknd
PUT - update an existing data entry in the bknd
DELETE - delete an existing data entry in the bknd
*/
```


```javascript
/*
GET method - https://jsonholder.com/todos

todo endpoint: "/todos"
it tells bknd what is requested from frontend

---------------------------------------------Respose Codes-------------------------------------------------
200 - Success
400 - Bad Request
401 - Unauthorized
404 - Not found
500 -  Something went Wrong
*/
```

## Intro to Json


```javascript
var object ={
    'name':'vasi',
    'lname':'l',
    'marks':[25,30,45],
    'rank':2,
    'married':false
}

console.log(object)
console.log(JSON.stringify(object)) // to convert JSON objects to Strings
console.log(JSON.parse(JSON.stringify(object))) // to convert JSON strings to JSON
```

    {
      name: 'vasi',
      lname: 'l',
      marks: [ 25, 30, 45 ],
      rank: 2,
      married: false
    }
    {"name":"vasi","lname":"l","marks":[25,30,45],"rank":2,"married":false}
    {
      name: 'vasi',
      lname: 'l',
      marks: [ 25, 30, 45 ],
      rank: 2,
      married: false
    }
    

## Intro to AJAX


```javascript
/*
AJAX -  asynchronous javascript and XML - exchanges data from front to back async - update the page without reloading the page
        - used to send and receive JSON objects - to run a part of code async in the backend (background execution)
        
        to ge get elements from the Backend
        
var http = new XMLHttpRequest()
http.open('method','link',true) true - async false -  sync
http.open('GET','https://jsonplaceholder.typicode.com/todos',true)
http.send()


eg: function

function getTodos(){
    var http = new XMLHttpRequest()
    http.open('method','link',true) true - async false -  sync
    http.open('GET','https://jsonplaceholder.typicode.com/todos',true)
    http.send()  // all api access can be seen in network section
}

getTodos()
*/
```

## Handling HTTP Responses


```javascript
/*
    The 'readyState' property - XMLHttpRequest property that  holds the status of the XMLHttpRequest
    
    These are the available status of the request.
    0 - UNSENT (request initiated open not called)
    1 - OPENED (open() has been called)
    2 - HEADERS RECEIVED (send() has been called)
    3 - LOADING (request is being processed)
    4 - DONE (request is completed and response is ready)
    
*/
```


```javascript
/*
    The 'onreadystateChange' property
        XMLHttpRequest property defines a function to be executed when a readystate changes.
*/
```


```javascript
/*
    eg( ) function getTodo(){
        var http = new XMLHttpRequest()
        http.open('GET','https://jsonplaceholder.typicode/todos',true)
        http.send()
        http.onreadystatechange=function(){
        if(this.readyState===4)
            {
                if(this.status===200)
                    console.log(this.responseText)
                else
                    console.log('call failed')
            }
        }
    }
*/
```


```javascript
/*
    http.onreadystatechange=function(){
                if(this.readyState===4)
                {
                    if(this.status===200)
                    {
                        var response=JSON.parse(this.responseText) // to convert json to objects
                        console.log(response[0],typeof(response[0]))
                        for (var i=0;i<=20;i++)
                        {
                            addElement(response[i].id,response[i].title)
                        }
                    }
                }
            }
        }

*/
```

## Intro To JQuery


```javascript
/*
    js library - fast,lightweight,feature-rich - principle('write less','do more') - supported by all browsers
    
    JQuery helps with following things
    - HTML,DOM manipulation
    - CSS Manipulation
    - Handling HTML Event
    - Effects and animations
    - Making AJAX calls
    
    Installing JQuery 
    JQuery cdn - minified
    
    (<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>)
*/
```

## Selectors and Filters


```javascript
/*
     Basic Syntax of jQuery
     
     $(selector).method()
     
     - $ used to access jQuery
     - 'selector' used to find HTML elements
     - 'method()' used to perform actions on html elements
*/
```


```javascript
/*
    Selectors and Filters provide a way of finding and extracting information from our web page
    
    ex: $('p') select all statements with a paragraph tag and use it as a list of objects
        $('#top-bar'), $('header section')
*/
```


```javascript
/*
    Filters are used to refine the results returned from the selectors.
    
    for example.
    
    $('p:first')
    this(':something') - is a filter that selects the first paragraph returned by $('p') selector
    
    the above line of code can also be written like this: $('p').first()
    similarly ($('p:last') - to select last, $('p').eq(n) -  n is the nth value starting from 0 index)
    
    $('input[type=text]')
    
    //to check if dom tree is ready
    $(document).ready(function()
    {
        console.log('DOM tree is ready')
    })
*/
```

## Adding or Updating HTML Elements


```javascript
/*
    the "html()" method - equivalent of innerHTML is the html() method.
    html() is used to get the content of the selected HTML element
    This content can either be text or more HTML elements
    
    Syntax:
    To get values: $('selector').html()
    to set values: $('selector').html(childElement)
    To appened child : $('selector').append(childElement)
    To remove child : $('selector').remove() to remove all childs
    to remove one child : $('selector').eq(n).remove() || $('selector:first').remove() || $('selector:last').remove()
    
    E.g. 
    (
        todoList.append(li1,li2,li3)
        $('li').eq(2).remove()
        console.log($('li').eq(2).html())
    )
*/
```

## Add and Updating Styles


```javascript
/*
    To get CSS of a html element - 'css(property)' method 
    it accepts css property and returns a value
    
    Syntax:
        $('selector').css('property-name')
        
        e.g. : $('li:first').css('background-color','lightpink')
               $('li:first').css({'background-color':'white','font-size':'48px'})
               $('li:first').css({'background-color':'white','font-size':'16px'})
               
               ------------------------- To add/remove/toggle Classes--------------------------
               
               $('li').eq(2).addClass('darkMode')
               $('li').eq(2).removeClass('darkMode')
               $('li').eq(2).toggleClass('darkMode')
*/
```

## Handling Events in jQuery


```javascript
/*
    Syntax: 
        $('selector').event-name(function(){
        //Do somethings
        })
        $('selector').click(function(){
        //Do somethings
        })

        $('selector').on(
        {'input':function(e){console.log(e.target.value)},
         'keyup':function(e)
             {
                 if(e.keyCode===13){ createElement()}
             }
        })
        
        value.value ='' is replaced by value.val('')
        
        e.g. : ( addBtn.click(function(){
            alert('button is clicked')
        })
         value.on({
             'input':function(e){console.log(e.target.value)},
             'change':function(){ value.val('')}
         }))
        
*/
```

## AJAX using jQuery


```javascript
/*
    jQuery supports ajax calls and it gives access to methods to make AJAX calls
    
    Syntax:
    $.get(URL,callback)
    callback is called when the function is completed.
    no need to create XMLHTTPrequest object or listen to status changes. jQuery handles everything for you.
    
    
    e.g.
    (
        $.get('https://jsonplaceholder.typicode.com/albums',function(data,status)
            {
                var response=data; 
                        console.log(response[0],typeof(response[0]),status)
                        for (var i=0;i<=10;i++)
                        {
                            addElement(response[i].title)
                        }
            })
    )
    
    
     $.post('https://jsonplaceholder.typicode.com/albums',todo,function() //todo - object to be added ,no need to covert JSON 
                {
                   
                   alert('task is added')
                   addElement(todo.title)

                }) 
                value.val(' ')
                }
*/
```


```javascript

```
