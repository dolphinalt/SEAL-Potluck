
## Potluck Food Items
*Please bring the food in a fancy plate/bowl that will look good for pictures :)*

<table id="foodTable">
    <tr>
        <td>Person</td>
        <td>Dish</td>
        <td>Notes</td>
        <td>Homemade/Store-bought</td>
        <td>Time to prepare</td>
    </tr>
    <tr>
        <td>Zhang Tianmin</td>
        <td>Dumplings (饺子)</td>
        <td>300+ dumplings with multiple fillings (60 each: beef, pork, lamb, shrimp, chives)</td>
        <td>Homemade</td>
        <td>the entire previous day</td>
    </tr>
    <tr>
        <td>Lu Yixuan</td>
        <td>Steamed fish (蒸鱼)</td>
        <td>Will keep the head and tail, also there should be some leftover at the end of the meal for good luck to follow Chinese tradition</td>
        <td>Homemade</td>
        <td>2 hours</td>
    </tr>
    <tr>
        <td>Wu Yuhan</td>
        <td>Spring rolls (春卷)</td>
        <td>appetizer</td>
        <td>Store-bought</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>Wu Yuhan</td>
        <td>Tea (茶)</td>
        <td>different flavors (ex: green tea, matcha, 菊花茶)</td>
        <td>Store-bought</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>Zhao Yuxuan</td>
        <td>Sweet rice balls (汤圆)</td>
        <td>buy multiple fillings (ex: sesame, peanuts, red bean paste)</td>
        <td>Store-bought</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>Tang Haoyu</td>
        <td>Noodles (面条)</td>
        <td>soup noodles</td>
        <td>Homemade</td>
        <td>50+ minutes</td>
    </tr>
    <tr>
        <td>Lu Meixi</td>
        <td>Broccoli and Beef (芥兰牛肉)</td>
        <td>traditional stir-fry</td>
        <td>Homemade</td>
        <td>25 minutes</td>
    </tr>
    <tr>
        <td>Wang Peng</td>
        <td>New Year Cake (年糕)</td>
        <td>dessert, includes red beans</td>
        <td>Homemade</td>
        <td>4 hours</td>
    </tr>
    <tr>
        <td>Zhang Xiaoxuan</td>
        <td>Scallion Pancakes (葱油饼)</td>
        <td>crispy and delicious</td>
        <td>Homemade</td>
        <td>1 hour 30 minutes</td>
    </tr>
    <tr>
        <td>Zhang Hao</td>
        <td>Wontons (馄钝汤)</td>
        <td>side of chili oil sauce for those who prefer spicy, 150+ wontons</td>
        <td>Homemade</td>
        <td>the entire previous day</td>
    </tr>
    <tr>
        <td>Wang Tianmin</td>
        <td>Fruits (水果)</td>
        <td>an assorment of fruits (ex: oranges)</td>
        <td>Store-bought</td>
        <td>N/A</td>
    </tr>
    <tr>
        <td>Wang Tianmin</td>
        <td>Water (水)</td>
        <td>bottled water</td>
        <td>Store-bought</td>
        <td>N/A</td>
    </tr>
</table>

## Dietary Preferences
*Please try to accomodate these dietary preferences with your dish*

<table>
    <tr>
        <td>Name</td>
        <td>Dietary Preferences</td>
    </tr>
    <tr>
        <td>Zhang Tianmin</td>
        <td>severely allergic to nuts</td>
    </tr>
    <tr>
        <td>Lu Yixuan</td>
        <td>lactose intolerant</td>
    </tr>
    <tr>
        <td>Wu Yuhan</td>
        <td>no dietary preferences</td>
    </tr>
    <tr>
        <td>Zhao Yuxuan</td>
        <td>doesn't like shellfish</td>
    </tr>
    <tr>
        <td>Tang Haoyu</td>
        <td>vegetarian</td>
    </tr>
    <tr>
        <td>Lu Meixi</td>
        <td>can't stand the smell of eggs</td>
    </tr>
    <tr>
        <td>Wang Peng</td>
        <td>allergic to soy</td>
    </tr>
    <tr>
        <td>Zhang Xiaoxuan</td>
        <td>doesn't like sweet things</td>
    </tr>
    <tr>
        <td>Zhang Hao</td>
        <td>can't handle spicy</td>
    </tr>
    <tr>
        <td>Wang Tianmin</td>
        <td>allergic to sesame</td>
    </tr>
</table>

# Add an entry
<table>
    <tr>
        <th><label for="name">Name</label></th>
        <th><label for="dish">Dish</label></th>
        <th><label for="notes">Notes</label></th>
        <th><label for="homemade">Homemade/Store-bought</label></th>
        <th><label for="time">Time to Prepare</label></th>
    </tr>
    <tr>
        <td><input type="text" name="name" id="name" required></td>
        <td><input type="text" name="dish" id="dish" required></td>
        <td><input type="text" name="notes" id="notes" required></td>
        <td><input type="text" name="homemade" id="homemade" required></td>
        <td><input type="text" name="time" id="time" required></td>
        <td ><button onclick="create_Entry()">Add</button></td>
    </tr>
</table>

# Remove an entry
<table>
    <tr>
        <th><label for="num">Entry Number to Remove</label></th>
    </tr>
    <tr>
        <td><input type="number" name="num" id="num" required></td>
        <td ><button onclick="delete_Entry()">Delete</button></td>
    </tr>
</table>

<script>
function create_Entry() {
  var table = document.getElementById("foodTable");
  var row = table.insertRow(1);
  var cell1 = row.insertCell(0);
  var cell2 = row.insertCell(1);
  var cell3 = row.insertCell(2);
  var cell4 = row.insertCell(3);
  var cell5 = row.insertCell(4);
  cell1.innerHTML = document.getElementById("name").value;
  cell2.innerHTML = document.getElementById("dish").value;
  cell3.innerHTML = document.getElementById("notes").value;
  cell4.innerHTML = document.getElementById("homemade").value;
  cell5.innerHTML = document.getElementById("time").value;
}

function delete_Entry() {
    var table = document.getElementById("foodTable");
    document.getElementsByTagName("tr")[document.getElementById("num").value].remove();
}

</script>