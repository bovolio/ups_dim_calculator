---
title: UPS
body_classes: 'title-center title-h1h2'
---

#UPS DIM Calculator
------------------

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
        document.getElementById('outcome').innerHTML = `${dim} lbs.`;
        document.getElementById('normalweight').innerHTML = `${weight} lbs.`;
        if(dim > weight){
            document.getElementById('billable-weight').innerHTML = `${dim} lbs.`;
        }
        else {
            document.getElementById('billable-weight').innerHTML = `${weight} lbs.`;
        };
    };
</script>
