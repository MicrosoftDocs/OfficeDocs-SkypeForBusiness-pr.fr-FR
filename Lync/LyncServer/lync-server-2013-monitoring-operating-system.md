---
title: 'Lync Server 2013 : surveillance du système d’exploitation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d6cad561761b7387cb4c268229f76b52f4bd24b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500631"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a>Surveillance du système d’exploitation dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-01-26_

Vous devez surveiller les performances de tous les serveurs et composants dans le Lync Server 2013. Évidemment, l’un des composants les plus importants est le système d’exploitation lui-même. Lync Server 2013 prend en charge les éditions x64 de :

  - Windows Server 2008 R2

  - Windows Server 2012 et Windows Server 2012 R2

Le moyen le plus transparent de surveiller un système d’exploitation consiste à utiliser le pack d’administration du système d’exploitation Windows Server. Elle offre des notions de base de surveillance fondamentales, telles que les performances, l’intégrité et la disponibilité des ordinateurs qui exécutent Windows Server 2012, Windows Server 2012 R2 et Windows Server 2008 R2.

En détectant, en alertant et en répondant automatiquement aux événements importants et aux indicateurs de performances, ces packs d’administration réduisent les temps de résolution des problèmes et augmentent la disponibilité et les performances globales des systèmes exécutant les systèmes d’exploitation Windows Server.

Outre les packs de gestion Windows Server appropriés pour System Center Operations Manager, les ressources et outils système suivants peuvent être utilisés pour surveiller l’état du système d’exploitation (en fonction de la version du système d’exploitation).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 inclut les fonctionnalités et outils supplémentaires suivants pour aider les administrateurs à utiliser la surveillance et la gestion des systèmes d’exploitation de base :

  - Le **moniteur de ressource Windows** est un outil puissant pour comprendre comment les ressources système sont utilisées par les processus et les services. En plus de surveiller l’utilisation des ressources en temps réel, un moniteur de ressources peut vous aider à analyser les processus qui ne répondent pas, à identifier les applications qui utilisent des fichiers et à contrôler les processus et les services.

  - Le **composant d’analyse de la fiabilité** est un agent intégré qui fournit des informations détaillées sur l’utilisation et la fiabilité du système. Ces informations sont exposées via une interface WMI afin de la mettre à la disposition des systèmes de lecteurs d’ordinateurs portables. En exposant le composant d’analyse de fiabilité via une interface WMI, les développeurs peuvent surveiller et analyser les applications, ce qui augmente la fiabilité et les performances.

  - **Windows Server 2008 R2** utilise le composant d’analyse de fiabilité intégré pour calculer un index de fiabilité, qui fournit des informations sur l’utilisation et la stabilité du système dans le temps. Le composant d’analyse de fiabilité effectue également le suivi des modifications importantes apportées au système susceptibles d’influencer la stabilité, telles que les mises à jour Windows et les installations d’applications.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Moniteur de fiabilité et de performances Windows Server 2008 Windows

L’analyseur de fiabilité et de performances Windows est un composant logiciel enfichable MMC qui combine les fonctionnalités des outils autonomes précédents, y compris les journaux et alertes de performance, le conseiller serveur de performance et le moniteur système. Il fournit une interface graphique pour la personnalisation des sessions de collecte de données de performances et de suivi d’événements.

Il inclut également le moniteur de fiabilité, un composant logiciel enfichable MMC qui effectue le suivi des modifications apportées au système et les compare aux modifications apportées à la stabilité du système, et fournit une vue graphique de leur relation.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Moniteur de fiabilité et de performances Windows

Bien que le moniteur de fiabilité et de performances de Windows combine les fonctionnalités de certains anciens outils autonomes, tels que les journaux et alertes de performance, ainsi que le moniteur système et le conseiller de performance de serveur, il fournit également de nouvelles fonctionnalités pour Windows Server 2008 et Windows Server 2008 R2, tels que les suivants :

  - Ensembles de collecteurs de données

  - Affichage des ressources

  - Moniteur de fiabilité

  - Assistants et modèles pour la création de journaux

**Ensemble de collecteur de données** regroupe les collecteurs de données en éléments réutilisables pour une utilisation avec différents scénarios d’analyse des performances. Une fois qu’un groupe de collecteurs de données est stocké en tant qu’ensemble de collecteur de données, des opérations telles que la planification peuvent être appliquées à l’ensemble du jeu par le biais d’une modification de propriété unique. L’analyseur de fiabilité et de performances de Windows inclut des modèles d’ensembles de collecteurs de données par défaut pour aider les administrateurs système à commencer immédiatement à collecter des données de performances propres à un rôle de serveur ou à un scénario de surveillance.

La page d’accueil de l’analyseur de fiabilité et de performances Windows est le nouvel écran de **vue des ressources** , qui fournit une représentation graphique en temps réel de l’utilisation de l’UC, du disque, du réseau et de la mémoire. En développant chacun de ces éléments surveillés, les administrateurs système peuvent identifier les processus qui utilisent les ressources. Dans les versions antérieures de Windows, ces données en temps réel, propres aux processus, étaient disponibles uniquement sous forme limitée dans le gestionnaire des tâches.

Le **moniteur de fiabilité** calcule un index de stabilité du système reflétant si des problèmes inattendus ont permis de réduire la fiabilité du système. Un graphique de l’index de stabilité au fil du temps identifie rapidement des dates lorsque des problèmes ont commencé. Le rapport de stabilité du système associé fournit des informations pour vous aider à résoudre la cause d’une fiabilité réduite. En affichant les modifications apportées au système (installation ou suppression d’applications, mises à jour du système d’exploitation ou ajout ou modification de pilotes) côte à côte avec des échecs (défaillances de l’application, panne du système d’exploitation ou défaillances matérielles), une stratégie de résolution des problèmes peut être développée rapidement.

L’ajout de compteurs aux fichiers journaux et la planification de leur démarrage, de leur arrêt et de leur durée peuvent désormais être effectués via une **interface d’Assistant**. De plus, l’enregistrement de cette configuration sous forme de modèle permet aux administrateurs système de collecter le même journal sur d’autres ordinateurs sans répéter la sélection du collecteur de données et les processus de planification. Les fonctionnalités journaux et alertes de performance ont été intégrées à l’analyseur de fiabilité et de performances de Windows pour être utilisées avec n’importe quel ensemble de collecteurs de données.

</div>

</div>

<span> </span>

</div>

</div>

</div>

