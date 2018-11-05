---
title: 'Lync Server 2013 : Composants utilisés par Response Group'
TOCTitle: Composants utilisés par Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425768(v=OCS.15)
ms:contentKeyID: 49296704
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants utilisés par Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-11_

L’application Response Group est automatiquement activée lors du déploiement de Voix Entreprise. Cette section présente les composants qui prennent en charge l’application Response Group.

## Composants de l’application Response Group

Les composants Microsoft Lync Server 2013 suivants prennent en charge l’application Response Group :

  - **service d’application** : le service d’application fournit une plateforme de déploiement, d’hébergement et de gestion des applications de communications unifiées, telles que Response Group. Le service d’application est automatiquement installé sur chaque serveur frontal d’un pool de serveurs frontaux et sur chaque serveur Standard Edition.

  - **application Response Group** : l’application Response Group est l’une des applications de communications unifiées hébergées par le service d’application. Elle est automatiquement incluse lors du déploiement de Response Group. L’application Response Group achemine les appels entrants destinés aux groupes d’agents et les place en file d’attente.

  - **Module linguistique** : un module linguistique est requis pour prendre en charge la conversion de texte par synthèse vocale et la reconnaissance vocale. Ces technologies vocales servent lors de la configuration de messages (message de bienvenue et autres messages, ou les questions et réponses d’une réponse vocale interactive, par exemple). Par défaut, 26 modules linguistiques pris en charge sont installés lors du déploiement de Lync Server 2013.

  - **Fichiers audio** : ils sont destinés aux messages et à la musique d’attente.

  - **Magasin de fichiers** : Response Group y stocke les fichiers audio. Plusieurs pools Response Group peuvent utiliser la même instance d’un magasin de fichiers.

  - **outil de configuration Response Group** : l’outil de configuration Response Group est un outil web permettant de créer et de configurer des groupes Response Group. L’outil de configuration Response Group est installé avec les services web.

  - **Panneau de configuration Microsoft Lync Server 2013** : le Panneau de configuration Lync Server permet d’installer et de configurer les groupes et les files d’attente d’agents pour les groupes Response Group.

  - **Lync Server Management Shell** : vous pouvez configurer tous les paramètres Response Group à l’aide des applets de commande Lync Server Management Shell.

  - **Microsoft Lync 2013** : les agents formels (ceux qui doivent se connecter au groupe pour recevoir des appels pour le groupe) utilisent Lync 2013 pour se connecter du groupe et s’en déconnecter. Si un groupe d’agents est configuré pour des agents formels, les agents se connectent au groupe et s’en déconnectent à partir d’une console web accessible depuis un élément de menu dans Lync 2013 qui permet d’ouvrir Internet Explorer.

  - **Services web** : les services web sont nécessaires à l’outil de configuration Response Group, à la console de connexion et de déconnexion des agents, au Panneau de configuration Lync Server et au service web client Response Group.

  - **Service web client Response Group** : l’application Response Group fournit un service web client que les applications tierces peuvent utiliser pour récupérer des informations sur les agents, les membres du groupe d’agents, le statut de connexion des agents, le statut des appels des groupes et les groupes qui prennent en charge les appels anonymes. Lync 2013 et Intendant Lync 2010 utilisent le service web client de Response Group pour récupérer la liste des groupes Response Group dont les agents peuvent se servir pour passer des appels anonymes. Le service web client est installé avec les services web.

