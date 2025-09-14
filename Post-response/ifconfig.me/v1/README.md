````js
// Récupérer la réponse de ton API
let apiResponse = pm.response.json();

// Appeler ifconfig.me en parallèle
pm.sendRequest("https://ifconfig.me", function (err, res) {
    if (!err) {
        let publicIP = res.text();
        
        // Afficher dans la console
        console.log("Mon IP publique:", publicIP);

        // Ajouter comme variable Postman
        pm.environment.set("publicIP", publicIP);

        // Tu peux aussi fusionner infos dans une variable
        pm.environment.set("apiPlusIP", {
            apiData: apiResponse,
            myIP: publicIP
        });
    }
});

````

---

## O/P
<img src="https://i.imgur.com/yJ23ScL.png">
