(function(){
  $('a').click(function() {
  $(this).addClass('actc').siblings().removeClass('actc');
});
var mySwiper = new Swiper ('.swiper-container', {
    direction: 'horizontal',
    loop: true,
    effect : 'coverflow',
  slidesPerView: 1.35,
  centeredSlides: true,
  coverflowEffect: {
    rotate: 0,
    stretch: 60,
    depth: 0,
    modifier: 1,

  },
    autoplay: {
    delay: 2000,
    stopOnLastSlide: false,
    disableOnInteraction: false,
    },
    navigation: {
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    },
    scrollbar: {
      el: '.swiper-scrollbar',
    },
  });
})();




(function(){
  var i = 0 ;
var timer;
 
$(document).ready(function(){
  //用jquery方法设置第一张图片显示，其余隐藏
  $('.ig').eq(0).show().siblings('.ig').hide();
   
  //调用showTime()函数（轮播函数）
  showTime();
   
  //当鼠标经过下面的数字时，触发两个事件（鼠标悬停和鼠标离开）
  $('.tab').hover(function(){
    //获取当前i的值，并显示，同时还要清除定时器
    i = $(this).index();
    Show();
    clearInterval(timer);
  },function(){
    //
    showTime();
  });
   
  //鼠标点击左侧的箭头
  $('.btn1').click(function(){
    clearInterval(timer);
    if(i == 0){
      i = 5;//注意此时i的值
    }
    i--;
    Show();
    showTime();
  });
   
  //鼠标点击右侧的箭头
  $('.btn2').click(function(){
    clearInterval(timer);
    if(i == 4){
      i = -1;//注意此时i的值
    }
    i++;
    Show();
    showTime();
  });
   
});
 
 
//创建一个showTime函数
function showTime(){
  //定时器
  timer = setInterval(function(){
    //调用一个Show()函数
    Show();
    i++;
    //当图片是最后一张的后面时，设置图片为第一张
    if(i==5){
      i=0;
    }
  },2500);
}
 
 
//创建一个Show函数
function Show(){
  //在这里可以用其他jquery的动画
  $('.ig').eq(i).fadeIn(300).siblings('.ig').fadeOut(300);
   
  //给.tab创建一个新的Class为其添加一个新的样式，并且要在css代码中设置该样式
  $('.tab').eq(i).addClass('act').siblings().removeClass('act');
   
  /*
   * css中添加的代码：
   * .bg{ background-color: #f00; }
   * */
}
})();

(function(){
  function $(id) {
    return document.getElementById(id);
  }
  var ind=0; // 正在显示的图片的序号(0开始)
  var imgW=960; // 图片宽度
  var box=$('ban2');
  var imgs=$('imgs');
  var buts=$('btn').getElementsByTagName('span');
  imgs.style.left=-imgW*ind+'px'; // 指定第ind个图像显示出来
  buts[ind].className='act'; // 指定第ind个按钮为active状态（class="act"）
  var butts=buts.length; // 按钮数量/图片数量
  var pr=$('shang');
  var ne=$('xia');
  var t=null;
  for(var i=0;i<butts;i++) {
    buts[i].i=i; //每个按钮设置js属性，保存序号
    buts[i].onmouseout=function(){ // 设置每个按钮的点击事件
      imgs.style.left=-imgW*this.i+'px';
      // 设置轮播图向指定方向移动指定距离
      // 距离计算：一幅图片宽度x按钮的序号
      buts[ind].className=''; // 清除掉上一个act状态的按钮
      ind=this.i; // 正在显示的图片的序号设置为被点击的按钮的序号
      this.className='act'; // 被点击的按钮设置为act状态
    }
  }
  function move(dir) {
    var oldInd=ind; // 保存上一个图片的序号
    ind=ind+dir; // 变化图片的序号
    // 过界处理
    if(ind<0){ // 如果小于最小序号
      ind=butts-1; // 设置为最大序号
    }
    if(ind>butts-1){ // 如果大于最大序号
      ind=0; // 设置为最小序号
    }
    imgs.style.left=-imgW*ind+'px'; // 指定第ind个图像显示出来
    buts[oldInd].className=''; // 清除掉上一个act状态的按钮
    buts[ind].className='act'; // 指定第index个按钮为active状态（class="act"）
  }
  pr.onclick=function(){
    move(-1);
    // 此时 dir=-1
    // index=index+dir
    // 等同于
    // index=index-1
    // 等同于index--
  }
  ne.onclick=function(){
    move(1);
    // 此时 dir=1
    // index=index+dir
    // 等同于
    // index=index+1
    // 等同于index++
  }
  box.onmouseover=function(){
    clearInterval(t);
  }
  box.onmouseout=function(){
    t=setInterval(ne.onclick,1000);
  }
  box.onmouseout();
})();


