---
title: 'Lync Server 2013 : Composants utilisés par l’application d’annonce'
TOCTitle: Composants utilisés par l’application d’annonce
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398608(v=OCS.15)
ms:contentKeyID: 49297824
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Composants utilisés par l’application d’annonce dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-13_

Dans Lync Server 2013, l’application d’annonce est un composant de l’application Response Group. Lorsque vous déployez Voix Entreprise, l’application d’annonce est installée et activée automatiquement avec l’application Response Group. Cette section présente les composants qui prennent en charge l’application d’annonce.

## Composants de l’application d’annonce

Les composants Lync Server suivants prennent en charge l’application d’annonce :

  - **service d’application**   Le service d’application fournit une plateforme pour le déploiement, l’hébergement et la gestion des applications de communications unifiées. Le service d’application est installé automatiquement sur chaque serveur frontal dans un pool de serveurs frontaux et sur chaque serveur Standard Edition.

  - **application Response Group**   L’application Response Group est l’une des applications de communication unifiées hébergées par le service d’application. Quand une plage de numéros de téléphone non attribués est configurée pour s’acheminer vers une annonce, l’application Response Group est requise pour acheminer les appels effectués vers le numéro de téléphone. (L’application Response Group n’est pas requise si toutes les plages sont configurées pour être acheminées vers la messagerie unifiée Exchange (UM).)

  - **Fichiers audio**   Les fichiers audio sont utilisés pour les annonces.

  - **Magasin de fichiers**   L’application d’annonce utilise un magasin de fichiers pour stocker ses fichiers audio.

  - **Panneau de configuration Lync Server**   Vous pouvez utiliser le Panneau de configuration Lync Server pour configurer la table des numéros non attribués.

  - **Lync Server Management Shell**   Vous pouvez utiliser les applets de commande Lync Server Management Shell pour configurer les paramètres d’annonce et la table des numéros non attribués.

