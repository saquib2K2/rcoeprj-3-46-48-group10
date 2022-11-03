var
inp\_as=document.getElementById('a\_size'),array\_size=inp\_as.value;
var inp\_gen=document.getElementById("a\_generate"); var
inp\_aspeed=document.getElementById("a\_speed");

var butts\_algos=document.querySelectorAll(".algos button");

var div\_sizes=\[\]; var divs=\[\]; var margin\_size; var
cont=document.getElementById("array\_container");
cont.style="flex-direction:row";

//Array generation and updation.

inp\_gen.addEventListener("click",generate\_array);
inp\_as.addEventListener("input",update\_array\_size);

function generate\_array() { cont.innerHTML=\"\";

    for(var i=0;i<array_size;i++)
    {
        div_sizes[i]=Math.floor(Math.random() * 0.5*(inp_as.max - inp_as.min) ) + 10;
        divs[i]=document.createElement("div");
        cont.appendChild(divs[i]);
        margin_size=0.1;
        divs[i].style=" margin:0% " + margin_size + "%; background-color:blue; width:" + (100/array_size-(2*margin_size)) + "%; height:" + (div_sizes[i]) + "%;";
    }

}

function update\_array\_size() { array\_size=inp\_as.value;
generate\_array(); }

window.onload=update\_array\_size();

//Running the appropriate algorithm. for(var
i=0;i\<butts\_algos.length;i++) {
butts\_algos\[i\].addEventListener("click",runalgo); }

function disable\_buttons() { for(var i=0;i\<butts\_algos.length;i++) {
butts\_algos\[i\].classList=\[\];
butts\_algos\[i\].classList.add("butt\_locked");

        butts_algos[i].disabled=true;
        inp_as.disabled=true;
        inp_gen.disabled=true;
        inp_aspeed.disabled=true;
    }

}

function runalgo() { disable\_buttons();

    this.classList.add("butt_selected");
    switch(this.innerHTML)
    {
        case "Bubble":Bubble();
                        break;
        case "Selection":Selection_sort();
                        break;
        case "Insertion":Insertion();
                        break;
        case "Merge":Merge();
                        break;
       
    }

}
