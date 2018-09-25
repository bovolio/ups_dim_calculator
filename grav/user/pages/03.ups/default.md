---
title: UPS
body_classes: 'title-center title-h1h2'
---

#UPS DIM Calculator
------------------
Large Package Surcharge
A Large Package Surcharge will be applied to each UPS package when its length plus girth [(2 x width) + (2 x height)] combined exceeds 130 inches, but does not exceed the maximum UPS size of 165 inches.

Large Packages are subject to a **minimum billable weight of 90 pounds in addition to the Large Package Surcharge.**


An Additional Handling charge will not be assessed when a Large Package Surcharge is applied.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

<div class=grid-container>
    <div class=grid-item-1>
    <br><br><br>
    <input type="text" id="length" placeholder=Length value="">
    <br><br><br> 
    <input type="text" id="width" placeholder=Width value="">
    <br><br><br>
    <input type="text" id="height" placeholder=Height value="">
    <br><br><br>
    <input type="text" id="weight" placeholder='Product Weight' value="">
    <br>
    <br>
    <button onclick="addUp()">DIM ME UP</button>
    </div>
    <div class=grid-item-2>
    </br>
    <p class='weightnames'>Dimensional Weight:</p><p id=outcome></p>
    </div>
    <div class=grid-item-3>
    </br>
    <p class='weightnames'>Actual Weight: </p><p id=normalweight></p>
    </div>
    <div class=grid-item-4>
    </br>
    <p class='weightnames'>Billable Weight: </p><p id=billable-weight class=billable-weight></p>
    </div>
</div>

<script>

    function addUp(){
        var length = parseFloat(document.getElementById('length').value);
        var width = parseFloat(document.getElementById('width').value);
        var height = parseFloat(document.getElementById('height').value);
        var weight = parseFloat(document.getElementById('weight').value);
        var dim = Math.round((length * width * height)/ 139);
        var girth = (2 * width) + (2 * height);
        
        document.getElementById('outcome').innerHTML = `${dim} lbs.`;
        document.getElementById('normalweight').innerHTML = `${weight} lbs.`;
        
        
        if((girth + length) > 130) {
            document.getElementById('billable-weight').innerHTML = `!THIS IS A LARGE PACKAGE!<br>AW: ${weight} lbs.<br>DIM: ${dim} lbs.`;
            console.log(girth);
        }
        else if(dim > weight){
            document.getElementById('billable-weight').innerHTML = `${dim} lbs.`;
        }
        else {
            document.getElementById('billable-weight').innerHTML = `${weight} lbs.`;
        };
    };
</script>
