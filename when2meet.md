## When are you available?


<style>
  td b{display:block;position:relative;color: rgba(0, 0, 0, 0);}
  td b:hover{background:rgba(255, 255, 255, 0.25);color: rgba(0, 0, 0, 0);}
</style>

<script>
  var UserData = [{"globalMap":[[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0]]},{"name":"Example","indMap":[[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0]]}]
  var map = [[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0]]
  var GlobalMap = [[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0]]
  function removeEmpty(obj) {
    return Object.fromEntries(Object.entries(obj).filter(([_, v]) => v != null));
  }
  function newUser() {
    console.log(UserData)
    var uid = document.getElementById("usernameinput").value;
    console.log(uid)
    for (var index = 1; index < UserData.length; ++index) {
      var existingUser = UserData[index];
      console.log(existingUser.name)
      if (existingUser.name == uid){
        alert("User " + uid + " already exists!")
        return 1;
      }
    }
    console.log("new user")
    alert("User " + uid + " created!")
    user = {name:uid,"indMap":[[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0],[0,0,0,0,0,0,0]]}
    UserData.push(user)
    return 0;
  }
  function deleteUser() {
    console.log(UserData)
    var uid = document.getElementById("usernameinput").value;
    console.log(uid)
    for (var index = 1; index < UserData.length; ++index) {
      var existingUser = UserData[index];
      console.log(existingUser.name)
      if (existingUser.name == uid){
        delete UserData[index]
        alert("User " + uid + " has been removed from database!")
        UserData = removeEmpty(UserData)
        UserData = Object.entries(UserData)
        return 0;
      }
    }
    alert("User " + uid + " has already been removed from the database!")
    console.log("User does not exist")
    return 0;
  }
  function cellSelect(row, column) {
    rowIdx = row-1
    columnIdx = column-1
    console.log(map[rowIdx][columnIdx])
    cell = document.getElementById(row + "," + column)
    if (map[rowIdx][columnIdx] == 0) {
      map[rowIdx][columnIdx] = 1
      GlobalMap[rowIdx][columnIdx] += 1
      cell.style.background = "#00FF00"
    } else if (map[rowIdx][columnIdx] == 1) {
      map[rowIdx][columnIdx] = 0
      GlobalMap[rowIdx][columnIdx] += 1
      cell.style.background = "rgba(0, 0, 0, 0)"
    }
    console.log(UserData)
  }
</script>

What is your name?
<form id="form" onsubmit="return false;">
  <input type = "text" id = "usernameinput">
  <input type = "submit" onclick = "newUser()">
  <button onclick = "deleteUser()">Cancel</button>
</form>

<table>
  <tr>
    <th></th>
    <th>Jan 22</th>
    <th>Jan 23</th>
    <th>Jan 24</th>
    <th>Jan 25</th>
    <th>Jan 26</th>
    <th>Jan 27</th>
    <th>Jan 28</th>
  </tr>
  <tr>
    <th>4:00</th>
    <td id = "1,1"><b onclick = "cellSelect(1,1)">0</b></td>
    <td id = "1,2"><b onclick = "cellSelect(1,2)">0</b></td>
    <td id = "1,3"><b onclick = "cellSelect(1,3)">0</b></td>
    <td id = "1,4"><b onclick = "cellSelect(1,4)">0</b></td>
    <td id = "1,5"><b onclick = "cellSelect(1,5)">0</b></td>
    <td id = "1,6"><b onclick = "cellSelect(1,6)">0</b></td>
    <td id = "1,7"><b onclick = "cellSelect(1,7)">0</b></td>
  </tr>
  <tr>
    <th>5:00</th>
    <td id = "2,1"><b onclick = "cellSelect(2,1)">0</b></td>
    <td id = "2,2"><b onclick = "cellSelect(2,2)">0</b></td>
    <td id = "2,3"><b onclick = "cellSelect(2,3)">0</b></td>
    <td id = "2,4"><b onclick = "cellSelect(2,4)">0</b></td>
    <td id = "2,5"><b onclick = "cellSelect(2,5)">0</b></td>
    <td id = "2,6"><b onclick = "cellSelect(2,6)">0</b></td>
    <td id = "2,7"><b onclick = "cellSelect(2,7)">0</b></td>
  </tr>
  <tr>
    <th>5:30</th>
    <td id = "3,1"><b onclick = "cellSelect(3,1)">0</b></td>
    <td id = "3,2"><b onclick = "cellSelect(3,2)">0</b></td>
    <td id = "3,3"><b onclick = "cellSelect(3,3)">0</b></td>
    <td id = "3,4"><b onclick = "cellSelect(3,4)">0</b></td>
    <td id = "3,5"><b onclick = "cellSelect(3,5)">0</b></td>
    <td id = "3,6"><b onclick = "cellSelect(3,6)">0</b></td>
    <td id = "3,7"><b onclick = "cellSelect(3,7)">0</b></td>
  </tr>
  <tr>
    <th>6:00</th>
    <td id = "4,1"><b onclick = "cellSelect(4,1)">0</b></td>
    <td id = "4,2"><b onclick = "cellSelect(4,2)">0</b></td>
    <td id = "4,3"><b onclick = "cellSelect(4,3)">0</b></td>
    <td id = "4,4"><b onclick = "cellSelect(4,4)">0</b></td>
    <td id = "4,5"><b onclick = "cellSelect(4,5)">0</b></td>
    <td id = "4,6"><b onclick = "cellSelect(4,6)">0</b></td>
    <td id = "4,7"><b onclick = "cellSelect(4,7)">0</b></td>
  </tr>
  <tr>
    <th>6:30</th>
    <td id = "5,1"><b onclick = "cellSelect(5,1)">0</b></td>
    <td id = "5,2"><b onclick = "cellSelect(5,2)">0</b></td>
    <td id = "5,3"><b onclick = "cellSelect(5,3)">0</b></td>
    <td id = "5,4"><b onclick = "cellSelect(5,4)">0</b></td>
    <td id = "5,5"><b onclick = "cellSelect(5,5)">0</b></td>
    <td id = "5,6"><b onclick = "cellSelect(5,6)">0</b></td>
    <td id = "5,7"><b onclick = "cellSelect(5,7)">0</b></td>
  </tr>
  <tr>
    <th>7:00</th>
    <td id = "6,1"><b onclick = "cellSelect(6,1)">0</b></td>
    <td id = "6,2"><b onclick = "cellSelect(6,2)">0</b></td>
    <td id = "6,3"><b onclick = "cellSelect(6,3)">0</b></td>
    <td id = "6,4"><b onclick = "cellSelect(6,4)">0</b></td>
    <td id = "6,5"><b onclick = "cellSelect(6,5)">0</b></td>
    <td id = "6,6"><b onclick = "cellSelect(6,6)">0</b></td>
    <td id = "6,7"><b onclick = "cellSelect(6,7)">0</b></td>
  </tr>
  <tr>
    <th>7:30</th>
    <td id = "7,1"><b onclick = "cellSelect(7,1)">0</b></td>
    <td id = "7,2"><b onclick = "cellSelect(7,2)">0</b></td>
    <td id = "7,3"><b onclick = "cellSelect(7,3)">0</b></td>
    <td id = "7,4"><b onclick = "cellSelect(7,4)">0</b></td>
    <td id = "7,5"><b onclick = "cellSelect(7,5)">0</b></td>
    <td id = "7,6"><b onclick = "cellSelect(7,6)">0</b></td>
    <td id = "7,7"><b onclick = "cellSelect(7,7)">0</b></td>
  </tr>
  <tr>
    <th>8:00</th>
    <td id = "8,1"><b onclick = "cellSelect(8,1)">0</b></td>
    <td id = "8,2"><b onclick = "cellSelect(8,2)">0</b></td>
    <td id = "8,3"><b onclick = "cellSelect(8,3)">0</b></td>
    <td id = "8,4"><b onclick = "cellSelect(8,4)">0</b></td>
    <td id = "8,5"><b onclick = "cellSelect(8,5)">0</b></td>
    <td id = "8,6"><b onclick = "cellSelect(8,6)">0</b></td>
    <td id = "8,7"><b onclick = "cellSelect(8,7)">0</b></td>
  </tr>
  <tr>
    <th>8:30</th>
    <td id = "9,1"><b onclick = "cellSelect(9,1)">0</b></td>
    <td id = "9,2"><b onclick = "cellSelect(9,2)">0</b></td>
    <td id = "9,3"><b onclick = "cellSelect(9,3)">0</b></td>
    <td id = "9,4"><b onclick = "cellSelect(9,4)">0</b></td>
    <td id = "9,5"><b onclick = "cellSelect(9,5)">0</b></td>
    <td id = "9,6"><b onclick = "cellSelect(9,6)">0</b></td>
    <td id = "9,7"><b onclick = "cellSelect(9,7)">0</b></td>
  </tr>
  <tr>
    <th>9:00</th>
    <td id = "10,1"><b onclick = "cellSelect(10,1)">0</b></td>
    <td id = "10,2"><b onclick = "cellSelect(10,2)">0</b></td>
    <td id = "10,3"><b onclick = "cellSelect(10,3)">0</b></td>
    <td id = "10,4"><b onclick = "cellSelect(10,4)">0</b></td>
    <td id = "10,5"><b onclick = "cellSelect(10,5)">0</b></td>
    <td id = "10,6"><b onclick = "cellSelect(10,6)">0</b></td>
    <td id = "10,7"><b onclick = "cellSelect(10,7)">0</b></td>
  </tr>
</table>

## When is the group available?

<table>
  <tr>
    <th></th>
    <th>Jan 22</th>
    <th>Jan 23</th>
    <th>Jan 24</th>
    <th>Jan 25</th>
    <th>Jan 26</th>
    <th>Jan 27</th>
    <th>Jan 28</th>
  </tr>
  <tr>
    <th>4:00</th>
    <td id = "glob1,1"></td>
    <td id = "glob1,2"></td>
    <td id = "glob1,3"></td>
    <td id = "glob1,4"></td>
    <td id = "glob1,5"></td>
    <td id = "glob1,6"></td>
    <td id = "glob1,7"></td>
  </tr>
  <tr>
    <th>5:00</th>
    <td id = "glob2,1"></td>
    <td id = "glob2,2"></td>
    <td id = "glob2,3"></td>
    <td id = "glob2,4"></td>
    <td id = "glob2,5"></td>
    <td id = "glob2,6"></td>
    <td id = "glob2,7"></td>
  </tr>
  <tr>
    <th>5:30</th>
    <td id = "glob3,1"></td>
    <td id = "glob3,2"></td>
    <td id = "glob3,3"></td>
    <td id = "glob3,4"></td>
    <td id = "glob3,5"></td>
    <td id = "glob3,6"></td>
    <td id = "glob3,7"></td>
  </tr>
  <tr>
    <th>6:00</th>
    <td id = "glob4,1"></td>
    <td id = "glob4,2"></td>
    <td id = "glob4,3"></td>
    <td id = "glob4,4"></td>
    <td id = "glob4,5"></td>
    <td id = "glob4,6"></td>
    <td id = "glob4,7"></td>
  </tr>
  <tr>
    <th>6:30</th>
    <td id = "glob5,1"></td>
    <td id = "glob5,2"></td>
    <td id = "glob5,3"></td>
    <td id = "glob5,4"></td>
    <td id = "glob5,5"></td>
    <td id = "glob5,6"></td>
    <td id = "glob5,7"></td>
  </tr>
  <tr>
    <th>7:00</th>
    <td id = "glob6,1"></td>
    <td id = "glob6,2"></td>
    <td id = "glob6,3"></td>
    <td id = "glob6,4"></td>
    <td id = "glob6,5"></td>
    <td id = "glob6,6"></td>
    <td id = "glob6,7"></td>
  </tr>
  <tr>
    <th>7:30</th>
    <td id = "glob7,1"></td>
    <td id = "glob7,2"></td>
    <td id = "glob7,3"></td>
    <td id = "glob7,4"></td>
    <td id = "glob7,5"></td>
    <td id = "glob7,6"></td>
    <td id = "glob7,7"></td>
  </tr>
  <tr>
    <th>8:00</th>
    <td id = "glob8,1"></td>
    <td id = "glob8,2"></td>
    <td id = "glob8,3"></td>
    <td id = "glob8,4"></td>
    <td id = "glob8,5"></td>
    <td id = "glob8,6"></td>
    <td id = "glob8,7"></td>
  </tr>
  <tr>
    <th>8:30</th>
    <td id = "glob9,1"></td>
    <td id = "glob9,2"></td>
    <td id = "glob9,3"></td>
    <td id = "glob9,4"></td>
    <td id = "glob9,5"></td>
    <td id = "glob9,6"></td>
    <td id = "glob9,7"></td>
  </tr>
  <tr>
    <th>9:00</th>
    <td id = "glob10,1"></td>
    <td id = "glob10,2"></td>
    <td id = "glob10,3"></td>
    <td id = "glob10,4"></td>
    <td id = "glob10,5"></td>
    <td id = "glob10,6"></td>
    <td id = "glob10,7"></td>
  </tr>
</table>