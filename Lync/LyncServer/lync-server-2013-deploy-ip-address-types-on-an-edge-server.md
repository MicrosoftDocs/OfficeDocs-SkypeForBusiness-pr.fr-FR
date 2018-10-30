---
title: 'Lync Server 2013 : Déploiement des types d’adresse IP sur un serveur Edge'
TOCTitle: Déploiement des types d’adresse IP sur un serveur Edge
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204984(v=OCS.15)
ms:contentKeyID: 49297569
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des types d’adresse IP sur un serveur Edge pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-06-14_

À partir du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur Edge.

## Pour déployer des types d’adresses IP sur un serveur Edge

1.  Dans le Générateur de topologie, sous **Pools de serveurs Edge** , cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés** . (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** à partir du menu **Action** .)

2.  Dans la fenêtre **Modifier les propriétés** , sélectionnez la configuration d’adresse IP à prendre en charge. Les figures suivantes illustrent une configuration double pile pour l’interface interne et l’interface externe.
    
    **Interface interne de serveur Edge à double pile**
    
    ![Page des propriétés générales Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Page des propriétés générales Lync Server")
    
    **Interface externe de serveur Edge à double pile**
    
    ![Page de configuration externe/tronçon suivant Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Page de configuration externe/tronçon suivant Lync Server")

3.  Pour chaque type d’adresse sélectionné, vous devez fournir des adresses internes et externes appropriées.

