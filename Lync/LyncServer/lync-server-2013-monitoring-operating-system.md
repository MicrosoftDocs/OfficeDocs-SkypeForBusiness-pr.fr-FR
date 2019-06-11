---
title: 'Skype Entreprise Server 2015 : surveillance du système d’exploitation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2f8124afcf2d1acbde3518ff625d528d6e34a3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Surveillance du système d’exploitation dans Skype Entreprise Server 2015

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-01-26_

Vous devez surveiller les performances de tous les serveurs et composants du serveur Lync Server 2013. Évidemment, lֹ’un des composants les plus importants est le système d’exploitation proprement dit. Lync Server 2013 prend en charge les éditions x64 de:

  - Windows Server 2008 R2

  - Windows Server 2012 et Windows Server 2012 R2

Le moyen le plus transparent de surveiller un système d’exploitation consiste à utiliser le Pack de gestion du système d’exploitation Windows Server. Il fournit les principales notions fondamentales sur le contrôle, telles que les performances, l’État et la disponibilité des ordinateurs exécutant Windows Server 2012, Windows Server 2012 R2 et Windows Server 2008 R2.

Si vous détectez, importez et répondez automatiquement aux événements importants et aux indicateurs de performance, ces modules de gestion réduisent les délais de résolution des problèmes et améliorent la disponibilité et les performances globales des systèmes exécutant Windows Server systèmes d’exploitation.

Outre les packs de gestion Windows Server appropriés pour System Center Operations Manager, les ressources et les outils système suivants peuvent être utilisés pour contrôler l’état du système d’exploitation (en fonction de la version du système d’exploitation).

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 inclut les fonctionnalités et outils supplémentaires suivants pour permettre aux administrateurs d’effectuer le suivi et la gestion de base du système d’exploitation:

  - L’**Analyseur de ressources Windows** est un outil puissant qui permet de comprendre comment les processus et les services utilisent les ressources système. Outre la surveillance de l’utilisation des ressources en temps réel, un analyseur des ressources peut aider à analyser les processus qui ne répondent pas, à identifier les applications qui utilisent des fichiers et à contrôler les processus et les services.

  - Le **Composant d’analyse de fiabilité** est un agent intégré qui fournit des informations détaillées sur l’utilisation du système et la fiabilité. Ces informations sont présentées dans l’interface de Windows Management Instrumentation (WMI) afin qu'elles puissent être réutilisées par les systèmes de lecture portables. En exposant le Composant d’analyse de fiabilité par le biais d’une interface WMI, les développeurs peuvent surveiller et analyser les applications, ce qui permet d’augmenter la fiabilité et les performances.

  - **Windows Server 2008 R2** utilise le composant analyse de fiabilité intégré pour calculer un index de fiabilité qui fournit des informations sur l’utilisation globale du système et sa stabilité dans le temps. The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Moniteur de fiabilité et de performances Windows Server 2008

L’Analyseur de fiabilité et de performances Windows est un composant logiciel enfichable de la console MMC (Microsoft Management Console), qui combine les fonctionnalités des outils autonomes précédents, dont Journaux et alertes de performance, Vérificateur des performances des serveurs et Moniteur système. Son interface graphique permet de personnaliser la collecte des données de performances et les sessions de trace d’événements.

Il inclut également le Moniteur de fiabilité, un composant logiciel enfichable de la console MMC (Microsoft Management Console), qui suit les modifications apportées au système, les compare aux variations de stabilité du système et fournit une représentation graphique de leur relation.

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Analyseur de fiabilité et de performances Windows

Même si la fiabilité et le moniteur de performance Windows combinent des fonctionnalités d’anciens outils autonomes, tels que les journaux et alertes de performance, et le moniteur système et le conseiller en matière de performance du serveur, il fournit également une nouvelle fonctionnalité à Windows Server 2008 et Windows Server 2008 R2, comme suit:

  - Ensembles de collecteurs de données

  - Affichage des ressources

  - Analyseur de fiabilité

  - Assistants et modèles pour créer des journaux

Un **ensemble de collecteurs de données** regroupe des collecteurs de données dans des éléments réutilisables à utiliser avec différents scénarios de performances. Une fois qu’un groupe de collecteurs de données est stocké dans un ensemble de collecteurs de données, des opérations, comme la planification, peuvent être appliquées à tout l’ensemble en modifiant simplement une propriété. L’Analyseur de fiabilité et de performances Windows inclut des modèles d’ensemble de collecteurs de données par défaut pour permettre aux administrateurs système de commencer immédiatement à collecter des données de performances spécifiques à un rôle ou à un scénario de surveillance.

La page d’accueil de l’Analyseur de fiabilité et de performances Windows est le nouvel écran **Affichage des ressources**, qui offre une vue graphique en temps réel de l’utilisation du processeur, des disques, du réseau et de la mémoire. En développant chacun des éléments surveillés, les administrateurs système peuvent identifier les processus qui utilisent des ressources. Dans les versions antérieures de Windows, ces données en temps réel sur les processus étaient disponibles sous forme limitée dans le Gestionnaire de tâches.

L’**Analyseur de fiabilité** calcule un indice de stabilité du système qui reflète les problèmes inattendus ayant eu une incidence négative sur la fiabilité. Une courbe de l’indice de stabilité dans le temps identifie rapidement les dates auxquelles les problèmes ont commencé à se produire. Le rapport de stabilité du système associé contient des détails permettant de corriger la cause de la perte de fiabilité. En affichant les modifications apportées au système (installation ou suppression d’applications, mises à jour du système d’exploitation, ajout ou modification de pilotes) en regard des échecs (échecs des applications, blocage du système d’exploitation, défaillances matérielles), il est possible de développer rapidement une stratégie pour résoudre ces problèmes.

Il est désormais possible d’ajouter des compteurs dans les fichiers journaux et de planifier leur début, leur fin et leur durée par le biais d’une **interface de type Assistant**. De plus, l’enregistrement de cette configuration sous forme de modèle permet aux administrateurs système de collecter le même journal sur les autres ordinateurs sans avoir à sélectionner de nouveau les collecteurs de données ou à planifier les processus. Les fonctionnalités de Journaux et alertes de performance ont été intégrées à l’Analyseur de fiabilité et de performances Windows pour une utilisation avec les ensembles de collecteurs de données.

</div>

</div>

<span> </span>

</div>

</div>

</div>

