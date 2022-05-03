# routing

# Approfondissement des protocoles de routage
![image](https://user-images.githubusercontent.com/83721477/166416048-00d682e9-a067-48c5-989b-576b7855d5d8.png)

## Qu'est-ce qu'un protocole de routage?
```
Le protocole de routage est le mécanisme par lequel des chemins sont sélectionnés dans un réseau pour acheminer les données d'un
expéditeur jusqu'à un ou plusieurs destinataires
```

En fonction du nombre de destinataires et de la manière de délivrer le message, on distingue :
* unicast, qui consiste à acheminer les données vers une seule destination déterminée,
<img src="https://user-images.githubusercontent.com/83721477/166416539-81c06acf-455c-47b8-bd61-a9e780bda4a4.png" width=50% height=50%>

* broadcast qui consiste à diffuser les données à toutes les machines,
<img src="https://user-images.githubusercontent.com/83721477/166416582-137d9fe4-06b2-41f1-aef3-fed3393888e6.png" width=50% height=50%>

* multicast qui consiste à délivrer le message à l'ensemble des machines manifestant un intérêt pour un groupe,
<img src="https://user-images.githubusercontent.com/83721477/166416598-75fde3bb-4154-4d97-8a44-2028dc07c8a5.png" width=50% height=50%>

* anycast qui consiste à délivrer les données à n'importe quel membre d'un groupe, mais généralement le plus proche, au sein du réseau.
<img src="https://user-images.githubusercontent.com/83721477/166416623-5fb5ecf0-5133-4d81-b33c-5571cab39155.png" width=50% height=50%>


## Protocoles de routage à état de lien
Les protocoles de routage à état de lien utilisent un algorithme efficace. Les routeurs construisent leurs tables de routage, en fonction du coût des différentes liaisons.
OSPF et ISIS sont des protocoles de routage à état de lien. Ils ont l’avantage d’avoir une convergence très rapide.

### MEMO
<hr>

* Dispose d’une vue commune de la topologie.
* Calcule le plus court chemin vers les autres routeurs.
* Mises à jour déclenchées par événement et convergence plus rapide.
* Passe les mises à jour du routage à état de liens aux autres routeurs.

<hr>

### Comment les informations de routage état de lien sont mises à jour ?
Le routage à état de liens utilise les fonctions suivantes:
* des mises à jour de routage à état de liens (LSA).
* une base de données topologique.
* l’algorithme du plus court chemin d’abord (SPF).
* l’arbre SPF résultant.
* une table de routage afin de déterminer les meilleurs chemins pour les paquets.

https://www.youtube.com/watch?v=sDnIRhiolp8

Exemple:<br>
![image](https://user-images.githubusercontent.com/83721477/166420552-750dc45a-0760-414e-a6b4-366caafe90e7.png)

## Protocoles de routage à vecteur de distance
**Routing by Rumor**
```
Les protocoles de routage à vecteur de distances permettent de construire des tables de routages sans aucune vision globale du
réseau. Le terme « vecteur » vient du faite, que le protocole manipule des tableaux vers les autres nœuds du réseau.
Et le mot « distance » est le nombre de sauts qui lui permet d’atteindre les autres routeurs. IGRP et RIP sont des
protocoles de routage à vecteur de distance.

```
https://www.youtube.com/watch?v=40b1bM_y0Ng<br>

### MEMO
<hr>

* Visualise la topologie du réseau du point de vue de leurs voisins.
* Ajoute des vecteurs de distance d’un routeur à l’autre.
* Mises à jour périodiques fréquentes et convergence lente.
* Passe des copies des tables de routage aux routeurs voisins.

<hr>

![image](https://user-images.githubusercontent.com/83721477/166420147-b68e6c67-2e51-4203-8b88-cd237bd951c0.png)
