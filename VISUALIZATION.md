//We only have to change background-color and height of the sorting
element.

var speed=1000;

inp\_aspeed.addEventListener("input",vis\_speed);

function vis\_speed() { var array\_speed=inp\_aspeed.value;
switch(parseInt(array\_speed)) { case 1: speed=1; break; case 2:
speed=10; break; case 3: speed=100; break; case 4: speed=1000; break;
case 5: speed=10000; break; }

    delay_time=10000/(Math.floor(array_size/10)*speed);        //Decrease numerator to increase speed.

}

var delay\_time=10000/(Math.floor(array\_size/10)\*speed); //Decrease
numerator to increase speed. var c\_delay=0;//This is updated ov every
div change so that visualization is visible.

function div\_update(cont,height,color) { window.setTimeout(function(){
cont.style=\" margin:0% \" + margin\_size + "%; width:" +
(100/array\_size-(2\*margin\_size)) + "%; height:" + height + "%;
background-color:" + color + ";"; },c\_delay+=delay\_time); }

function enable\_buttons() { window.setTimeout(function(){ for(var
i=0;i\<butts\_algos.length;i++) { butts\_algos\[i\].classList=\[\];
butts\_algos\[i\].classList.add("butt\_unselected");

            butts_algos[i].disabled=false;
            inp_as.disabled=false;
            inp_gen.disabled=false;
            inp_aspeed.disabled=false;
        }
    },c_delay+=delay_time);

}
