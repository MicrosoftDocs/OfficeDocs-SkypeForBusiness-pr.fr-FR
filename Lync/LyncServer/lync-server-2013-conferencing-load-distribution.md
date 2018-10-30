---
title: Distribution de la charge des conférences
TOCTitle: Distribution de la charge des conférences
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204922(v=OCS.15)
ms:contentKeyID: 49297313
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Distribution de la charge des conférences

 

_**Dernière rubrique modifiée :** 2012-10-22_

Contrairement à d’autres solutions de conférence dédiées, l’architecture de Lync Server est celle d’un modèle matériel partagé. Cela signifie que le même matériel est partagé par de nombreux composants logiciels, chacun prenant en charge différentes communications en temps réel. Chaque type de communication en temps réel impose des charges spécifiques aux serveurs. Par exemple, le serveur frontal peut exécuter les composants de routage SIP (Session Initiation Protocol), des applications web (par exemple la recherche du carnet d’adresses), le service de conférence web, le service de conférence A/V, des applications Voix Entreprise (par exemple l’application Intendant Conférence et l’application Response Group), ainsi que le serveur de médiation. Un ensemble de bases de données situées sur le serveur frontal offrent également des fonctionnalités de stockage et de traitement des données relatives aux utilisateurs, aux contacts, à la présence, aux conférences et au routage de la voix. Avec ce partage du matériel, les composants, les services et les processus se répartissent les ressources de l’UC et de la mémoire. C’est la raison pour laquelle les charges non liées aux conférences ont un impact direct sur la montée en charge du serveur.

Comparée à d’autres solutions de conférence matérielles basées sur les ports, l’architecture de conférence de Lync Server est un modèle sans réservation. Quand un utilisateur planifie une réunion, Lync Server crée un enregistrement dans la base de données de conférence, qui stocke les données de conférence, mais ne réserve pas à l’avance les ressources matérielles de la réunion. À la place, Lync Server dispose d’une logique d’équilibrage de charge intégrée qui permet d’allouer dynamiquement les ressources de conférence sur les serveurs frontaux afin de répartir les charges uniformément entre tous les serveurs frontaux du pool. Cela permet d’approvisionner et d’utiliser les ressources matérielles mais rend difficile la prise en charge des réunions de très grande taille (surtout sans planification appropriée). Par exemple, quand un pool Lync Server 2013 est proche de sa capacité maximale, chaque serveur frontal peut héberger environ 125 réunions de taille moyenne. L’ajout d’une autre réunion de petite taille ne serait pas un obstacle alors que l’ajout d’une réunion de 1 000 utilisateurs serait un problème, car le serveurs frontaux ne pourrait probablement pas prendre en charge une si grande réunion en même temps que les 125 autres réunions.

