# Elementor vertical slider
Elementor vertical slider (content slide)
#Elementor Vertical Carousel without plugin

you should create page in elementor then create one section and insert your inner section
![image](https://user-images.githubusercontent.com/95649368/156922112-16259e11-da6d-418c-b3a7-54c9dd7daf34.png)
#
**After that, give a class name to the section that houses all these inner sections**
![image](https://user-images.githubusercontent.com/95649368/156922280-bff3fe6c-2130-4222-8c99-9fbc4b3037e1.png)

Give it the class name of 'parentsection'.


![image](https://user-images.githubusercontent.com/95649368/156922301-9199c7cf-9dbf-43fa-bb09-6d2cdab91b2d.png)

Also give a class name to all these inner sections
Give them the class name of 'swipee'. The name 'swipee' is used that it does not interfere with other classes in the Elementor library.

# Then, add this code to the Elementor htmlEditor:
```
<script src="https://unpkg.com/swiper/swiper-bundle.min.js"></script>
<script>
if (window.innerWidth > 1024){
let parent = document.querySelector('.parentsection .elementor-widget-wrap');
let children = parent.querySelectorAll('.swipee');
let wrapper = document.createElement('div');
wrapper.className = 'swiper-wrapper';

children.forEach((child) => {
wrapper.appendChild(child);
child.classList.add('swiper-slide');
});

let container = document.createElement('div');
container.className = 'swiper-container';

container.prepend(wrapper);

parent.prepend(container);

let pagination = document.createElement('div');
pagination.className = 'swiper-pagination';
container.prepend(pagination);

var swiper = new Swiper('.swiper-container', {
direction: 'vertical',
slidesPerView: 1,
spaceBetween: 30,
mousewheel: {
releaseOnEdges:true,
},
pagination: {
el: '.swiper-pagination',
clickable: true,
},
navigation: {
nextEl: '.swipee-down',
prevEl: '.swipee-up',
},
});
}
</script>

<style>
.elementor-element.elementor-absolute.swipee-up, .elementor-element.elementor-absolute.swipee-down{
z-index: 99;
cursor: pointer;
line-height: 0;
}
.parentsection .swiper-wrapper{
height: 800px; /* Height of swiper */
}
.parentsection .swiper-pagination{
transform: scale(2.6);
padding-right: 4px
}
</style>
```
this function just fine work in elementor pro 

**you can put this class .swipee-down for content (when user click on this content slide down)**

and you can delete ```direction: 'vertical',``` this code to create horizontal slider


#
my tg channel : https://t.me/AppDUNY
my tg username : https://t.me/DeAref
