---
title: 'Lync Server 2013: création d’une stratégie de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d378c66ae820ef0be7b7b3b0492b023863e977ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Établissement d’une stratégie de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-26_

Pour pouvoir développer un plan de sauvegarde et de restauration pour Lync Server, vous devez développer une stratégie adaptée aux objectifs de votre organisation. Pour développer une stratégie efficace de sauvegarde et de restauration, vous devez:

  - Définissez les priorités de votre entreprise.

  - Identifiez les exigences de sauvegarde et de restauration.

<div>

## <a name="establishing-business-priorities"></a>Établissement de priorités métiers

Évaluez les priorités des entreprises de votre organisation. En règle générale, les priorités principales pour les entreprises qui affectent votre stratégie de sauvegarde et de restauration sont les suivantes:

  - Exigences de continuité d’activité

  - Exhaustivité des données

  - Criticité des données

  - Exigences en matière de portabilité

  - Contraintes de coût

Les besoins de votre entreprise, tels que ceux-ci, permettent de déterminer les contrats de niveau de service (SLA) que vous développez auprès de vos clients. Les contrats de niveau de service influent grandement sur votre stratégie de sauvegarde et de récupération.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identification des exigences de sauvegarde et de restauration

Les priorités de votre entreprise et les accords de niveau de service agissent pour déterminer les besoins de votre organisation pour la sauvegarde et la restauration de Lync Server. Identifiez et documentez vos exigences pour ce qui suit:

  - **Fréquence des sauvegardes**   pour plus d’informations sur les meilleures pratiques en matière de fréquence de sauvegarde, voir [meilleures pratiques pour la sauvegarde et la restauration de Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Les outils**   de sauvegarde et de restauration incluent qui consiste à utiliser les outils, et sur quels ordinateurs. Pour plus d’informations sur les outils mentionnés dans cette rubrique et les autorisations nécessaires, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013: outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Emplacement de sauvegarde**   : Déterminez si les sauvegardes sont conservées localement ou à distance, en tenant compte de la sécurité et de l’accessibilité. Spécifiez le média à utiliser pour les sauvegardes.

  - **Configuration matérielle et logicielle requise**   identification et documentation de vos exigences matérielles et logicielles spécifiques, y compris le matériel pour le stockage de sauvegarde et la restauration de composants spécifiques et des logiciels et de la connectivité réseau requis pour Prenez en charge la sauvegarde et la restauration. Lorsque vous développez votre configuration matérielle et logicielle, n’oubliez pas les différents scénarios de restauration suivants.

  - **Scénarios de restauration**   Voici les processus de restauration des scénarios suivants:
    
      - Échec d’un pool de serveurs Lync. Ce scénario nécessite la reconstitution de chaque serveur dans le pool.
    
      - Un serveur Standard Edition Server échoue. Ce scénario nécessite la reconstitution du serveur sur un nouvel ordinateur ou un nouvel ordinateur et la restauration de bases de données.
    
      - Perte de la boutique centrale de gestion. Ce scénario nécessite au minimum la restauration et la publication du magasin central de gestion.
    
      - Perte d’un serveur principal lorsque le magasin central de gestion continue de fonctionner correctement. Ce scénario nécessite la reconstitution du serveur sur un nouvel ordinateur ou un nouvel ordinateur et la restauration de bases de données.
    
      - Un serveur qui fait partie d’un pool de serveurs Lync échoue. Ce scénario nécessite le réfection du serveur sur un nouvel ordinateur ou un nouvel ordinateur.
    
      - Un magasin de fichiers échoue. Ce scénario nécessite la restauration du serveur de fichiers ou du groupe de fichiers.
    
      - Une base de données de chat d’archivage, de surveillance ou persistante ne fonctionne pas. Ce scénario nécessite une recréation des bases de données, et si les données sont importantes pour votre organisation, la restauration des données. Il n’est pas nécessaire d’archiver, de surveiller et de discussions permanentes sur le serveur Lync.

</div>

</div>

<span> </span>

</div>

</div>

</div>

