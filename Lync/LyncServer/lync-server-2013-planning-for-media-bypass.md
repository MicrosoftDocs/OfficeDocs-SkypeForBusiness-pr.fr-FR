---
title: 'Lync Server 2013 : Planification de la déviation du trafic multimédia'
TOCTitle: Planification de la déviation du trafic multimédia
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398703(v=OCS.15)
ms:contentKeyID: 49298010
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

La déviation du trafic multimédia fait référence à la suppression du serveur de médiation du chemin d’accès des médias, dans le mesure du possible, pour les appels dont la signalisation traverse le serveur de médiation.

La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels. L’extensibilité peut être améliorée du fait que l’élimination du traitement multimédia pour les appels contournés réduit la charge sur le serveur de médiation. Cette réduction en termes de charge s’ajoute à la capacité du serveur de médiation à contrôler plusieurs passerelles.

Là où un site de succursale sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante restreinte, la déviation du trafic multimédia réduit les besoins en bande passante en permettant au média du client d’un site de succursale de s’acheminer directement vers sa passerelle locale sans avoir besoin de passer par la liaison de réseau étendu vers le serveur de médiation sur le site central et inversement.

En libérant le serveur de médiation du traitement multimédia, la déviation du trafic multimédia peut également réduire le nombre de serveurs de médiation requis par une infrastructure Voix Entreprise.

La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.

**Médias et voies de signalisation avec et sans déviation du trafic multimédia**

![Application de connexion de contournement de média CAC vocal](images/Gg398529.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de connexion de contournement de média CAC vocal")

En règle générale, essayez d’activer la déviation du trafic multimédia quand cela est possible.

## Dans cette section

  - [Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Modes de déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

## Sections connexes

[Déploiement des fonctionnalités avancées de Voix Entreprise dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

## Voir aussi

#### Tâches

[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Concepts

[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)

