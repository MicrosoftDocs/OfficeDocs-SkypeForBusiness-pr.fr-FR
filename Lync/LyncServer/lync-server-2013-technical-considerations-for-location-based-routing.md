---
title: 'Lync Server 2013 : Considérations techniques relatives au routage géodépendant'
TOCTitle: Considérations techniques relatives au routage géodépendant
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994027(v=OCS.15)
ms:contentKeyID: 53095389
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Considérations techniques relatives au routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-09_

Lorsque vous planifiez le routage géodépendant, vous devez tenir compte de l’impact des scénarios suivants.

## Récupération d’urgence

En cas de basculement du pool principal vers un pool de sauvegarde, ainsi que lors du rétablissement du fonctionnement normal vers le pool principal, le routage géodépendant reste appliqué tout le temps pendant la procédure de récupération d’urgence.

## Survivable Branch Appliance

La configuration du routage géodépendant affecte la planification de l’emplacement de déploiement des passerelles associées à vos serveurs Survivable Branch Appliance. La passerelle associée à votre Survivable Branch Appliance doit être située dans le même site réseau que votre Survivable Branch Appliance. Sinon, les utilisateurs hébergés dans votre Survivable Branch Appliance ne seront pas autorisés à passer des appels sortants si le routage géodépendant est configuré. Lorsque la connexion de réseau étendu entre votre Survivable Branch Appliance et le site central est interrompue, les restrictions de routage géodépendant restent appliquées.

## Voir aussi

#### Autres ressources

[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

