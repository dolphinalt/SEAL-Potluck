## Housing Overview
> We will meet at Zhang Tianming's house on January 22, 2023. If you have any requests or concerns please reach him at **858-123-5692** or **[zhang.tianming@gmail.com](mailto:zhang.tianming@gmail.com)**  
(DON'T ACTUALLY SPAM THIS ADDRESS)




<table id="test">
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Phone number</th>
        <th>Coming?</th>
    </tr>
    <tbody id="guestInfo"></tbody>
   

</table>



<br>
<br>
## Confirm that you are coming

Name?  <input type="text" id="name">
<button onclick="confirmation()">Confirm</button>


<script>
    const json = '[{"_name": "Zhang Tianming", "_age": 18, "_phoneNum": "858-123-5692", "_coming": true}, {"_name": "Lu Yixuan", "_age": 16, "_phoneNum": "858-237-4837", "_coming": true}, {"_name": "Wu Yuhan", "_age": 16, "_phoneNum": "858-263-1829", "_coming": true}, {"_name": "Tang Haoyu", "_age": 15, "_phoneNum": "858-182-3910", "_coming": true}, {"_name": "Zhao Yuxuan", "_age": 16, "_phoneNum": "858-192-8204", "_coming": true}, {"_name": "Lu Meixi", "_age": 17, "_phoneNum": "858-529-6629", "_coming": true}, {"_name": "Wang Peng", "_age": 18, "_phoneNum": "280-649-3947", "_coming": false}, {"_name": "Zhang Xiaoxuan", "_age": 45, "_phoneNum": "344-283-9483", "_coming": true}, {"_name": "Zhang Hao", "_age": 78, "_phoneNum": "329-394-3820", "_coming": false}, {"_name": "Wang Tianming", "_age": 44, "_phoneNum": "858-283-9938", "_coming": true}]';
    const data = JSON.parse(json); 


    data.forEach(addGuestInfo);

    function addGuestInfo(info) {
        let tr = document.createElement("tr"); 
        let name = document.createElement("td"); 
        name.innerHTML = info._name; 
        let age = document.createElement("td");
        age.innerHTML = info._age; 
        let phoneNum = document.createElement("td");
        phoneNum.innerHTML = info._phoneNum; 
        let coming = document.createElement("td");

        if (info._coming == true) { 
            coming.innerHTML = "Yes"; 
        } else {
            coming.innerHTML = "Not decided"; 
        }


        tr.appendChild(name); 
        tr.appendChild(age);
        tr.appendChild(phoneNum);
        tr.appendChild(coming);

        if (info._coming == false) {
            let userName = info._name;
            userName = userName.replace(/\s/g, '');
            userName = userName.charAt(0).toLowerCase() + userName.slice(1); 

            let tr2 = document.createElement("tr");

            let tbody = document.createElement("tbody");
            tbody.setAttribute("id", userName);

            tr2.appendChild(name); 
            tr2.appendChild(age);
            tr2.appendChild(phoneNum);

            tbody.appendChild(coming);

            tr2.appendChild(tbody)
            document.getElementById("test").appendChild(tr2);
        } else {

            document.getElementById("guestInfo").appendChild(tr);
        }

    }

    


    console.log(data); 


    function confirmation() {
        let nameInput = document.getElementById("name").value;
        nameInput = nameInput.replace(/\s/g, '');
        nameInput = nameInput.charAt(0).toLowerCase() + nameInput.slice(1); 

        document.getElementById(nameInput).innerText = "Yes";
    }

</script>


