
# Preparation Certification  CCNA


---

# **Résumé CCNA – Compagnon d'Étude Complet**

## **Introduction**

Le certificat CCNA (Cisco Certified Network Associate) est une qualification fondamentale pour les professionnels des réseaux. Il valide la maîtrise des concepts réseau de base, des protocoles de routage et de commutation, de la sécurité, et bien plus encore. Ce guide a été conçu pour offrir une compréhension complète et approfondie des différents sujets abordés dans l'examen CCNA.

Les chapitres qui suivent fourniront des explications détaillées pour chaque sujet, des exemples de configurations pratiques, des définitions claires et des illustrations afin d'aider les débutants à assimiler les concepts complexes. À la fin de chaque chapitre, vous trouverez également des questions pour vous tester sur vos acquis.

---

## **Sommaire**

1. **Fondamentaux des Réseaux**
2. **Adressage IP et Subnetting**
3. **Protocoles de Routage**
4. **Commutation et VLANs**
5. **Sécurité Réseau**
6. **Listes de Contrôle d’Accès (ACLs)**
7. **Protocoles WAN**
8. **OSPF (Open Shortest Path First)**
9. **Configuration et Gestion des Switches**
10. **Introduction aux VPNs et à la Sécurité Avancée**

---

## **1. Fondamentaux des Réseaux**

### **Modèles OSI et TCP/IP**
Le **modèle OSI** (Open Systems Interconnection) et le modèle **TCP/IP** sont les fondations de l'architecture réseau moderne. Le modèle OSI, constitué de 7 couches, permet de comprendre comment les données sont transmises d’un ordinateur à un autre à travers un réseau.

#### **Détails du modèle OSI :**
- **Couche 1 – Physique** : Concernée par la transmission physique des données via des câbles (cuivre, fibre optique) ou des signaux sans fil.
- **Couche 2 – Liaison de données** : Gère l’accès au médium et la détection des erreurs.
- **Couche 3 – Réseau** : Responsable du routage des paquets via des adresses IP.
- **Couche 4 – Transport** : Assure la fiabilité des transmissions via TCP ou UDP.
- **Couche 5 – Session** : Gère les sessions de communication entre les applications.
- **Couche 6 – Présentation** : Formate les données pour qu’elles soient comprises par l’application de destination.
- **Couche 7 – Application** : Interface avec les logiciels utilisateurs (HTTP, FTP, DNS).

| **Couche OSI** | **Exemple de Protocole** | **Rôle** |
|---|---|---|
| Couche 1 | Ethernet | Transmission physique des bits |
| Couche 3 | IP | Routage des paquets à travers les réseaux |
| Couche 4 | TCP, UDP | Contrôle du flux et de l’intégrité des données |

### **Modèle TCP/IP**
Le modèle **TCP/IP**, quant à lui, est plus simple et utilisé principalement sur Internet. Il se compose de 4 couches :
1. **Accès réseau**
2. **Internet**
3. **Transport**
4. **Application**

### **Meilleures pratiques** :
- **Apprendre les couches OSI et TCP/IP** en détail pour diagnostiquer les problèmes réseau efficacement.
- Maîtriser les protocoles **TCP/IP** est indispensable pour configurer et dépanner les réseaux modernes.

### **Exemple pratique** :
Imaginons que vous envoyez un e-mail. Ce message passe par les différentes couches, du niveau application (SMTP) au niveau physique (transmission des bits sur le câble Ethernet). Lorsque le destinataire reçoit cet e-mail, le processus est inversé : les bits sont convertis en données au niveau application.

---

## **2. Adressage IP et Subnetting**

### **Adresses IPv4**
Une adresse **IPv4** est composée de 32 bits, divisés en 4 octets. Elle se présente sous la forme d’un nombre décimal séparé par des points (ex. 192.168.1.1). Ces adresses sont réparties en deux types : **privées** et **publiques**.

#### **Types d'adresses IPv4 :**
- **Privées** : Réservées pour les réseaux internes et ne sont pas routables sur Internet (ex. 192.168.0.0/16, 10.0.0.0/8).
- **Publiques** : Routables sur Internet et attribuées par des organismes comme l’IANA.

| **Type d'adresse** | **Exemple** | **Utilisation** |
|---|---|---|
| Publique | 203.0.113.1 | Internet |
| Privée | 192.168.1.1 | Réseau local |

### **Subnetting**
Le **subnetting** est la technique qui permet de diviser un réseau en plusieurs sous-réseaux. Cela améliore l'efficacité de l'utilisation des adresses IP et réduit la taille des domaines de diffusion.

#### **Exemple de subnetting** :
- **Réseau initial** : 192.168.1.0/24
- **Subnet de 64 adresses** : 192.168.1.0/26
- **Hôtes disponibles par sous-réseau** : 62

| **Sous-réseau** | **Adresse de sous-réseau** | **Plage d’adresses** |
|---|---|---|
| 1er sous-réseau | 192.168.1.0/26 | 192.168.1.1 à 192.168.1.62 |
| 2e sous-réseau | 192.168.1.64/26 | 192.168.1.65 à 192.168.1.126 |

### **Meilleures pratiques** :
- Toujours planifier vos sous-réseaux en fonction du nombre d’hôtes que vous devez supporter.
- Utiliser des outils comme **IP subnet calculators** pour éviter les erreurs dans le calcul des sous-réseaux.

---

## **3. Protocoles de Routage**

### **Routage Statique**
Le **routage statique** est une méthode où les routes sont configurées manuellement sur chaque routeur. Cette méthode est simple mais peu flexible pour les grands réseaux.

#### **Exemple de configuration de route statique** :
```bash
Router(config)# ip route 10.1.1.0 255.255.255.0 10.1.2.1
```

### **Protocoles de Routage Dynamiques**
Les **protocoles de routage dynamiques** comme **RIP**, **OSPF** et **EIGRP** permettent aux routeurs d'échanger automatiquement des informations de routage. Ils s’adaptent aux changements du réseau sans nécessiter d'intervention manuelle.

#### **RIP (Routing Information Protocol)**
- **Distance Administrative** : 120
- **Caractéristiques** : Protocole basé sur le nombre de sauts, maximum 15 sauts.

#### **OSPF (Open Shortest Path First)**
- **Distance Administrative** : 110
- **Caractéristiques** : Basé sur l'algorithme SPF (Shortest Path First), utilise des zones pour organiser le routage.

| **Protocole** | **Avantages** | **Inconvénients** |
|---|---|---|
| RIP | Simple à configurer | Limite de 15 sauts, peu évolutif |
| OSPF | Très évolutif, rapide | Complexité de configuration |

### **Meilleures pratiques** :
- Utiliser des **protocoles de routage dynamiques** pour des réseaux de taille moyenne à grande.
- Configurer des routes statiques pour des liaisons simples ou des réseaux de petite taille.

---

## **4. Commutation et VLANs**

### **VLANs (Virtual Local Area Network)**
Un **VLAN** est une technologie qui permet de segmenter logiquement un réseau physique en plusieurs réseaux virtuels. Cela améliore la sécurité et la gestion des ressources au sein du réseau.

#### **Exemple de configuration d’un VLAN** :
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Sales
```

### **Trunking**
Le **trunking** permet à plusieurs VLANs de partager une seule connexion physique entre deux switches en utilisant le protocole **802.1Q**.

#### **Exemple de configuration Trunk** :
```bash
Switch(config)# interface GigabitEthernet0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# switchport trunk allowed vlan 10,20
```

| **VLAN ID** | **Nom** | **Réseau** |
|---|---|---|
| 10 | Sales | 192.168.10.0/24 |
| 20 | IT | 192.168.20.0/24 |

### **Meilleures pratiques** :
- Toujours configurer les VLANs pour segmenter les différents services ou départements.
- Utiliser **VLANs** pour isoler les segments du réseau et réduire les domaines de diffusion.

---
