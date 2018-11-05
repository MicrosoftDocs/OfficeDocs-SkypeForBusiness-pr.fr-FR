---
title: 'Lync Server 2013 : Déploiement des types d’adresses IP sur un serveur frontal'
TOCTitle: Déploiement des types d’adresses IP sur un serveur frontal
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205191(v=OCS.15)
ms:contentKeyID: 49298610
ms.date: 07/28/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des types d’adresses IP sur un serveur frontal pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-07-28_

À partir du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur frontal.

## Pour déployer des types d’adresses IP sur un serveur frontal

1.  Sous **Pools frontaux Enterprise Edition** , cliquez avec le bouton droit sur le serveur d’un pool, puis sélectionnez **Modifier les propriétés** . (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action** .)

2.  Dans la boîte de dialogue **Modifier les propriétés** , sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6** , comme illustré dans la figure suivante.
    
    **Boîte de dialogue Modifier les propriétés du pool de serveurs frontaux**
    
    ![Boîte de dialogue Modifier les propriétés du serveur frontal](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Boîte de dialogue Modifier les propriétés du serveur frontal")
    
      - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.
        
        > [!NOTE]  
        > Cette option est recommandée pour les configurations IP version 6 (IPv6).    
      - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour spécifier une adresse spécifique à utiliser sur le nouveau serveur. Si vous la sélectionnez, vous devez entrer une valeur pour **Adresse IP principale** .
    
      - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
      - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.

