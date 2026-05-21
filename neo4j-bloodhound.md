
### 1. Purge Neo4j actuel

```bash
sudo apt purge neo4j -y
sudo apt autoremove -y
```

---

### 2. Ajouter dépôt officiel Neo4j

```bash
sudo apt update
sudo apt install wget gnupg -y

wget -O - https://debian.neo4j.com/neotechnology.gpg.key | sudo gpg --dearmor -o /usr/share/keyrings/neo4j.gpg

echo "deb [signed-by=/usr/share/keyrings/neo4j.gpg] https://debian.neo4j.com stable 5" | sudo tee /etc/apt/sources.list.d/neo4j.list

sudo apt update
```

---

### 3. Réinstaller Neo4j proprement

```bash
sudo apt install neo4j -y
```

---

### 4. Vérifier service systemd

```bash
systemctl list-unit-files | grep neo4j
```

---

### 5. Activer et démarrer

```bash
sudo systemctl enable neo4j
sudo systemctl start neo4j
sudo systemctl status neo4j
```

---

### 6. Initialiser mot de passe

```bash
sudo neo4j-admin dbms set-initial-password 'BloodHound123!'
```

---

### 7. Vérification ports

```bash
ss -lntp | grep -E "7474|7687"
```

---

### 8. Lancer BloodHound

```bash
bloodhound-start
```

It seems it's the first time you run bloodhound
Please run bloodhound-setup first

Do you want to run bloodhound-setup now? [Y/n] Y

 [*] Starting PostgreSQL service

 [*] Creating Database
User _bloodhound already exists in PostgreSQL
Database bloodhound already exists in PostgreSQL
ALTER ROLE

 [*] Starting neo4j
Neo4j is running at pid 51861

 [i] You need to change the default password for neo4j
     Default credentials:
         user: neo4j
         password: neo4j

 [!] IMPORTANT: Once you have setup the new password, please update /etc/bhapi/bhapi.json with the new password before running bloodhound

 opening http://localhost:7474/

---

