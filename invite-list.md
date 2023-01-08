## Housing Overview
> We will meet at Zhang Tianming's house on January 22, 2023. If you have any requests or concerns please reach him at **858-123-5692** or **[zhang.tianming@gmail.com](mailto:zhang.tianming@gmail.com)**  
(DON'T ACTUALLY SPAM THIS ADDRESS)




<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Phone number</th>
        <th>Coming?</th>
    </tr>
    <tr>
        <td>Zhang Tianming</td>
        <td>18</td>
        <td> 858-123-5692</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Lu Yixuan</td>
        <td>16</td>
        <td> 858-123-5692</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Wu Yuhan</td>
        <td>16</td>
        <td> 858-263-1829 </td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Zhao Yuxuan</td>
        <td>16</td>
        <td>858-192-8204</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Tang Haoyu</td>
        <td>15</td>
        <td> 	858-182-3910</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Lu Meixi</td>
        <td>17</td>
        <td> 858-529-6629</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Wang Peng</td>
        <td>18</td>
        <td> 	280-649-3947</td>
        <td id="wangPeng">Not decided</td>
    </tr>
    <tr>
        <td>Zhang Xiaoxuan</td>
        <td>45</td>
        <td> 344-283-9483</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>Zhang Hao</td>
        <td>78</td>
        <td> 	329-394-3820</td>
        <td id="zhangHao">Not decided</td>
    </tr>
    <tr>
        <td>Wang Tianmin</td>
        <td>44</td>
        <td> 858-283-9938</td>
        <td>Yes</td>
    </tr>
</table>


<br>
<br>

## Confirm that you are coming

Name?  <input type="text" id="name">
<button onclick="confirmation()">Confirm</button>

<script>
    function confirmation() {
        let nameInput = document.getElementById("name").value;
        nameInput = nameInput.replace(/\s/g, '');
        nameInput = nameInput.charAt(0).toLowerCase() + nameInput.slice(1); 

        document.getElementById(nameInput).innerText = "Yes";
    }
</script>
