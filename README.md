- 👋 Hi, I’m @hosseinfarvahar
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
hosseinfarvahar/hosseinfarvahar is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
var slide = document.getElementsByClassName('slide');
var dot = document.getElementsByClassName('dot');
var prev = document.querySelector('.prev');
var next = document.querySelector('.next');
var n = 0;
var i;

function disno(){
    for( i = 0 ; i<slide.length ; i++){
        slide[i].style.display = 'none';
    }
}

function no_active(){
    for( i = 0 ; i<dot.length ; i++){
        dot[i].classList.remove('active');
    }
}

next.addEventListener('click',function(e){
    e.preventDefault();
    n++;
    if( n > slide.length - 1){ // length starts From 1
        n = 0; // Arrays Starts From zero
    }
    disno();
    no_active()
    slide[n].style.display = 'block';
    dot[n].classList.add('active');
})

prev.addEventListener('click',function(e){
    e.preventDefault();
    n--;
    if( n < 0){ // length starts From 1
        n = slide.length - 1; // Arrays Starts From zero
    }
    disno();
    no_active()
    slide[n].style.display = 'block';
    dot[n].classList.add('active');
})

setInterval(function(){
    n++;
    if( n > slide.length - 1){ // length starts From 1
        n = 0; // Arrays Starts From zero
    }
    disno();
    no_active()
    slide[n].style.display = 'block';
    dot[n].classList.add('active');
},3000)

