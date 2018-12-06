---
title: Prise en charge du matériel de périphérique dans Lync Server 2013
TOCTitle: 'Prise en charge du matériel de périphérique '
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412908(v=OCS.15)
ms:contentKeyID: 49298662
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge du matériel de périphérique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous devez mettre en place des configurations matérielles spécifiques avant de déployer des téléphones IP et des périphériques analogiques.

Les téléphones IP exécutant Lync Phone Edition prennent en charge PoE (Power over Ethernet) et le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discovery). Pour utiliser le protocole LLDP-MED, le commutateur doit prendre en charge les normes IEEE802.1AB et ANSI/TIA-1057. Pour utiliser PoE, il doit prendre en charge la norme PoE802.3AF ou 802.3at.

Pour utiliser LLDP-MED, l’administrateur doit activer LLDP dans la fenêtre de la console du commutateur et définir la stratégie réseau LLDP-MED à l’aide de l’ID du réseau local virtuel (VLAN) de voix correct.

De plus, si votre déploiement inclut des périphériques analogiques, vous devez configurer la passerelle analogique pour utiliser Lync Server, et la passerelle doit être l’un des composants suivants :

  - Un adaptateur de téléphone analogique (ATA)

  - Une passerelle analogique RTC

  - Un Survivable Branch Appliance qui inclut une passerelle analogique RTC

  - Un Survivable Branch Appliance qui inclut une passerelle RTC communiquant avec un adaptateur de téléphone analogique (ATA)

Pour savoir comment configurer une passerelle analogique, reportez-vous à « Planification du déploiement des périphériques analogiques », à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537), dans la bibliothèque TechNet Lync Server 2010. (Les périphériques analogiques fonctionnent de la même manière dans Lync Server 2013 que dans Lync Server 2010.)

> [!IMPORTANT]  
> Vous pouvez configurer le commutateur pour Enhanced 9-1-1 (E9-1-1) si celui-ci prend en charge cette fonctionnalité.
