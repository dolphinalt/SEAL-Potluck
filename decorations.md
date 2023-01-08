## Decorations for New Year
> Please help us purchase some decorations for our feast, it really helps to brighten up the mood!

<table id="decorations">
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
    </tr>
        <td><strong>Total</strong></td>
        <td> - </td>
        <td id="totalPrice"></td>
        <td></td>
</table>

<button onclick="calculatePrice()">Calculate Total</button>

<script>
    function calculatePrice()
    {
        let decorations = window.document.getElementById("decorations"); 
        let num_rows = decorations.rows.length;
        let total = 0;
        for (let i = 0; i<num_rows-1; i++) {
            let price = decorations.rows[i].cells[2].innerHTML.slice(1);
            let priceInt = parseInt(price);
            total+=priceInt;
        }
        let totalPrice = window.document.getElementById("totalPrice");
        totalPrice.innerHTML = calculatePrice();
    }   
    
</script>