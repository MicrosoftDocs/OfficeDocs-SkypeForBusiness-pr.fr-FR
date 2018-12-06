---
title: 'Lync Server 2013 : Estimation du trafic et de l’utilisation de la voix'
TOCTitle: Estimation du trafic et de l’utilisation de la voix
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398439(v=OCS.15)
ms:contentKeyID: 49297395
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Estimation du trafic et de l’utilisation de la voix pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-08-07_

L’outil de planification Microsoft Lync Server 2013 utilise la mesure suivante pour estimer le trafic utilisateur sur chaque site et le nombre de ports nécessaires à la prise en charge de ce trafic.

  -   
    Pour **Faible trafic** (1 appel RTC par utilisateur et par heure), 15 utilisateurs par port.

  -   
    Pour **Trafic moyen** (2 appels RTC par utilisateur et par heure), 10 utilisateurs par port.

  -   
    Pour **Trafic important** (au moins 3 appels RTC par utilisateur et par heure), 5 utilisateurs par port.

Le nombre de ports détermine ensuite le nombre de serveurs de médiation et de passerelles qui seront utilisés. La taille des passerelles de réseau téléphonique commuté (RTC) que la plupart des organisations envisagent de déployer peut aller de 2 à 960 ports. (Il existe des passerelles encore plus importantes, mais celles-ci sont principalement utilisées par des fournisseurs de services téléphoniques.)

Par exemple, une organisation comportant 10 000 utilisateurs et dont le trafic est moyen requiert 1 000 ports. Le nombre de passerelles requis est égal au nombre total de ports requis, qui est déterminé par la capacité totale des passerelles.

