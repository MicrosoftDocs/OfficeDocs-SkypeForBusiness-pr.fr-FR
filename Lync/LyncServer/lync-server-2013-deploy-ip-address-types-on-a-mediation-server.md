---
title: "Lync Server 2013 : Dépl. des types d’adresse IP sur un serveur de médiation"
TOCTitle: Déploiement des types d’adresse IP sur un serveur de médiation
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204964(v=OCS.15)
ms:contentKeyID: 49297483
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement des types d’adresse IP sur un serveur de médiation pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-07-28_

À partir du Générateur de topologie, effectuez les étapes de la procédure suivante pour déployer des types d’adresses IP sur un serveur de médiation.

## Pour déployer des types d’adresses IP sur un serveur de médiation

  - Dans le Générateur de topologie, sous **Pools de médiation**, cliquez avec le bouton droit sur le serveur au sein d’un pool, puis sélectionnez **Modifier les propriétés**. (Vous pouvez également sélectionner le serveur, puis cliquer sur **Modifier les propriétés** dans le menu **Action** )

  - Dans la boîte de dialogue **Modifier les propriétés**, sélectionnez le type d’adresse IP à configurer. S’il s’agit d’une configuration double pile, sélectionnez **Activer IPv4** et **Activer IPv6**, comme illustré dans la figure suivante.
    
    **Boîte de dialogue Modifier les propriétés pour le pool de serveurs de médiation**
    
    ![Page des propriétés générales Lync Server avec FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Page des propriétés générales Lync Server avec FQDN")
    
      - **Utiliser toutes les adresses IP configurées** : sélectionnez cette option pour autoriser l’utilisation de n’importe quelle adresse IP définie sur l’ordinateur à utiliser.
        
        > [!NOTE]  
        > Cette option est recommandée pour les configurations IP version 6 (IPv6).    
      - **Limiter l’utilisation des services aux adresses IP sélectionnées** : sélectionnez cette option pour indiquer une adresse spécifique à utiliser sur le nouveau serveur. Si vous sélectionnez cette option, vous devez entrer une valeur pour l’adresse IP principale.
    
      - **Adresse IP principale** : entrez l’adresse IP que le serveur utilisera pour toutes les communications autres que celles effectuées via le réseau téléphonique commuté (RTC). Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
    
      - **Adresse IP RTC** : entrez l’adresse IP RTC à utiliser lorsqu’un serveur de médiation est colocalisé sur le serveur frontal. Cette adresse IP doit correspondre au format du type d’adresse que vous avez sélectionné.
        
        > [!NOTE]  
        > L’installation de cartes d’interface réseau (NIC) supplémentaires afin de prendre en charge la configuration de l’adresse IP PSTN pour Lync Server 2013 n’est pas prise en charge. Pour plus d’informations sur les configurations NIC prises en charge Lync Server 2013, reportez-vous à la rubrique <a href="lync-server-2013-server-hardware-platforms.md">Plateformes matérielles de serveur pour Lync Server 2013</a>.
