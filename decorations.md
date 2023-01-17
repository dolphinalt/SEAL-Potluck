## Decorations for New Year
> Please help us purchase some decorations for our feast, it really helps to brighten up the mood!

<style>
        
</style>
<table id="decorations" onload="calculatePrice()">
    <tr>
        <th>Decoration</th>
        <th>Buyer</th>
        <th>Price</th>
        <th>Bought?</th>
    </tr>
    <tr>
        <td>Fireworks</td>
        <td>Lu Yixuan and Lu Meixi</td>
        <td>$74.99</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>Red paper Lanterns</td>
        <td>Zhang Tianming and Wu Yuhan</td>
        <td>$34.65</td>
        <td>no</td>
    </tr>
    <tr>
        <td>Paper cuttings</td>
        <td>Tang Haoyu</td>
        <td>$14.99</td>
        <td>no</td>
    </tr>
    <tr>
        <td>Upside-Down 福 Characters</td>
        <td>N/A</td>
        <td>$32.49</td>
        <td>no</td>
    </tr>
    <tr>
        <td>Paper Door Banners</td>
        <td>Zhao Yuxuan</td>
        <td>$32.49</td>
        <td>yes</td>
    </tr>
    <tr>
        <td>New Year Paintings</td>
        <td>Wang Peng</td>
        <td>$62.99</td>
        <td>yes</td>
    </tr>
    <tr>
        <td><strong>Total</strong></td>
        <td> - </td>
        <td id="totalPrice"></td>
        <td></td>
    </tr>
</table>

<table>
    <tr>
        <th><label for="decoration">Decoration</label></th>
        <th><label for="buyer">Buyer</label></th>
        <th><label for="price">price</label></th>
        <th><label for="bought">bought</label></th>
        <th></th>
    </tr>
    <tr>
        <td><input type="text" name="decoration" id="decoration" required></td>
        <td><input type="text" name="buyer" id="buyer" required></td>
        <td><input type="text" name="price" id="price" required></td>
        <td><input type="text" name="bought" id="bought" required></td>
        <td><button onclick="addItem()">Add Entry</button></td>
    </tr>
</table>

<table style="border-spacing: 30px;">
    <tr style="border-spacing: 30px;">
        <button onclick="calculatePrice()">Calculate Total</button><br>
    </tr>
</table>

<script>
    function calculatePrice()
    {
        let decorations = window.document.getElementById("decorations"); 
        let num_rows = decorations.rows.length;
        let total = 0;
        for (let i = 1; i<num_rows-1; i++) {
            let price = decorations.rows[i].cells[2].innerHTML.slice(1);
            let priceInt = parseFloat(price);
            total+=priceInt;
        }
        total = parseFloat(total).toFixed(2)
        let totalPrice = window.document.getElementById("totalPrice");
        totalPrice.innerHTML = "$".concat(String(total));
    }   

    function addItem()
    {
        // We grab our values from the table
        let decoration = window.document.getElementById("decoration").value;
        let buyer = window.document.getElementById("buyer").value;
        let price = window.document.getElementById("price").value;
        let bought = window.document.getElementById("bought").value;
        let decorations = window.document.getElementById("decorations"); 
        let insertRow = decorations.rows.length-1;
        let row = decorations.insertRow(insertRow)
        let rdec = row.insertCell(0);
        let rbuy = row.insertCell(1);
        let rprice = row.insertCell(2);
        let rbought = row.insertCell(3);

        rdec.innerText = decoration
        rbuy.innerText = buyer
        rprice.innerText = price
        rbought.innerText = bought
    }   
    
</script>