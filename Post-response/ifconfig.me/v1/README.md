````js
pm.sendRequest("https://ifconfig.me/all", function (err, res) {
    if (!err) {
        let body = res.text();   // ça donne un texte brut
        // On récupère seulement la ligne avec ip_addr
        let match = body.match(/ip_addr:\s*([0-9\.]+)/);
        if (match) {
            let ip = match[1];
            console.log("Mon IP publique:", ip);

            // Optionnel : stocker dans une variable
            pm.environment.set("publicIP", ip);
        }
    }
});
````

---

## O/P
<img src="https://i.imgur.com/3LI3A5e.png">
