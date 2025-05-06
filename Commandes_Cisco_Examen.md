
# Commandes Cisco Essentielles – Examen Pratique (Année 2)

---

## 🔧 Configuration de base

- `enable`  
  → Passe en mode privilégié (EXEC).

- `configure terminal`  
  → Accède au mode de configuration globale.

- `hostname NomDuRouteur`  
  → Change le nom du périphérique.

- `no shutdown`  
  → Active une interface désactivée.

- `exit`  
  → Sort du mode de configuration actuel.

---

## 🌐 Configuration des interfaces

- `interface FastEthernet0/0`  
  → Accède à l'interface Fa0/0.

- `interface GigabitEthernet0/1`  
  → Accède à l'interface Gi0/1.

- `ip address 192.168.1.1 255.255.255.0`  
  → Attribue une adresse IP et un masque de sous-réseau.

- `no shutdown`  
  → Active l'interface.

- `description Lien-vers-Switch`  
  → Ajoute une description à l'interface.

---

## 🔄 Routage (statique, RIP, OSPF)

### ➤ Routage statique

- `ip route 192.168.2.0 255.255.255.0 192.168.1.2`  
  → Crée une route statique vers un réseau distant.

### ➤ RIP

- `router rip`  
  → Active le protocole RIP.

- `version 2`  
  → Utilise RIP version 2 (supporte les masques CIDR).

- `network 192.168.1.0`  
  → Spécifie le réseau à annoncer.

- `no auto-summary`  
  → Désactive le résumé automatique de routes.

### ➤ OSPF

- `router ospf 1`  
  → Active OSPF avec le numéro de processus 1.

- `network 192.168.1.0 0.0.0.255 area 0`  
  → Indique le réseau à annoncer dans l’aire 0.

---

## 🔒 Sécurité et mots de passe

- `enable secret monpass`  
  → Définit un mot de passe chiffré pour le mode privilégié.

- `line console 0`  
  → Accède à la ligne console.

- `password consolepass`  
  → Définir un mot de passe pour la console.

- `login`  
  → Active l'authentification par mot de passe.

- `line vty 0 4`  
  → Accède aux lignes VTY (Telnet/SSH).

- `password telnetpass`  
  → Définit un mot de passe pour l’accès distant.

- `login`  
  → Active l'authentification sur VTY.

- `service password-encryption`  
  → Chiffre les mots de passe en clair dans la config.

---

## 📶 DHCP (sur routeur)

- `ip dhcp pool NOM_POOL`  
  → Crée un nouveau pool DHCP.

- `network 192.168.1.0 255.255.255.0`  
  → Définit le réseau à distribuer.

- `default-router 192.168.1.1`  
  → Définit la passerelle par défaut.

- `dns-server 8.8.8.8`  
  → Définit le serveur DNS.

- `exit`  
  → Quitte le pool DHCP.

- `ip dhcp excluded-address 192.168.1.1 192.168.1.10`  
  → Exclut des adresses de la distribution DHCP.

---

## 📁 VLAN & Trunking (sur switch)

- `vlan 10`  
  → Crée le VLAN 10.

- `name Ventes`  
  → Nomme le VLAN.

- `interface FastEthernet0/1`  
  → Accède à l'interface Fa0/1.

- `switchport mode access`  
  → Configure l’interface en mode accès.

- `switchport access vlan 10`  
  → Associe l’interface au VLAN 10.

- `interface FastEthernet0/24`  
  → Accède à l’interface Fa0/24.

- `switchport mode trunk`  
  → Configure l’interface en mode trunk.

---

## 📶 STP (Spanning Tree Protocol)

- `spanning-tree vlan 1 priority 4096`  
  → Définit la priorité STP pour le VLAN 1 (plus faible → Root Bridge).

---

## 📦 Port-Security (sur switch)

- `interface FastEthernet0/1`  
  → Accède à l’interface Fa0/1.

- `switchport mode access`  
  → Met le port en mode accès.

- `switchport port-security`  
  → Active la sécurité de port.

- `switchport port-security maximum 1`  
  → Autorise 1 seule adresse MAC.

- `switchport port-security violation shutdown`  
  → Ferme le port en cas de violation.

- `switchport port-security mac-address sticky`  
  → Apprend automatiquement l’adresse MAC et la rend persistante.

---

## 🔍 Commandes de vérification

- `show running-config`  
  → Affiche la configuration en cours.

- `show ip interface brief`  
  → Résumé des interfaces et adresses IP.

- `show vlan brief`  
  → Affiche les VLANs et les ports associés.

- `show mac address-table`  
  → Affiche la table d’adresses MAC.

- `show ip route`  
  → Affiche la table de routage.

- `show version`  
  → Infos système (IOS, mémoire, matériel).

- `show cdp neighbors`  
  → Affiche les voisins Cisco détectés.

- `ping [adresse IP]`  
  → Teste la connectivité réseau.

- `traceroute [adresse IP]`  
  → Montre le chemin suivi jusqu'à une destination.

---

## 💾 Sauvegarde & redémarrage

- `copy running-config startup-config`  
  → Sauvegarde la config actuelle.

- `reload`  
  → Redémarre le périphérique.
