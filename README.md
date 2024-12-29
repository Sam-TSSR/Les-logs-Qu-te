# Challenge

### 1. **Démarrer une machine virtuelle**
D'abord, crée une machine virtuelle avec un système **Debian**.

### 2. **Installer Apache**
Apache est un serveur web qui permet d'afficher des sites internet.

#### Pour installer Apache :
1. Ouvre le terminal et tape cette commande :
   ```bash
   apt update
   apt install apache2 -y

2. Lance Apache avec cette commande :
   ```bash
   systemctl start apache2
  
### 3. **Génèrer du trafic au serveur**

Pour envoyer du trafic :
1. Ouvre ton navigateur et tape http://localhost. C'est l'adresse de ton serveur.

2. Ou, utilise cette commande dans le terminal :
   ```bash
   curl http://localhost

### 4. Analyse les logs générés et identifie

1. Demandes réussies **code 200** :
Les demandes réussies ont le code 200. Pour les voir, tape cette commande :
    ```bash
    grep '200' /var/log/apache2/access.log

2. Erreurs **code 404** :
Les erreurs comme "page non trouvée" ont le code 404. Pour les voir, tape cette commande :
     ```bash
    grep '404' /var/log/apache2/access.log

3. Les adresses IP les plus fréquentes :
Pour les voir, tape cette commande :
     ```bash
     awk '{print $1}' /var/log/apache2/access.log | sort | uniq -c | sort -n

