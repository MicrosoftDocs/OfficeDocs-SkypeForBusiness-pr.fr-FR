---
title: 'Lync Server 2013 : établissement d’une stratégie de sauvegarde et de restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e281b85879063cacb9538d03fe221a4bf96b6bc5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514211"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Établissement d’une stratégie de sauvegarde et de restauration pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-26_

Avant de pouvoir développer un plan de sauvegarde et de restauration pour Lync Server, vous devez développer une stratégie adaptée aux objectifs de votre organisation. Pour développer une stratégie de sauvegarde et de restauration efficace, vous devez :

  - Établir les priorités de l’entreprise.

  - Identifier les besoins en matière de sauvegarde et de restauration.

<div>

## <a name="establishing-business-priorities"></a>Définition des priorités de l’entreprise

Évaluez les priorités de votre organisation. Habituellement, les principales priorités de l’entreprise qui ont des répercussions sur votre stratégie de sauvegarde et de restauration sont les suivantes :

  - Besoins de continuité de l’activité

  - Exhaustivité des données

  - Sensibilité des données

  - Besoins de portabilité

  - Contraintes budgétaires

Les besoins de l’entreprise, tels que ceux-ci, permettent de déterminer les contrats de niveau de service (SLA) que vous développez avec vos clients. Les contrats de niveau de service influencent considérablement votre stratégie de sauvegarde et de restauration.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identification des besoins de sauvegarde et de restauration

Les priorités de votre entreprise et les contrats de niveau de service agissent dans la détermination de la configuration requise de votre organisation pour la sauvegarde et la restauration de Lync Server. Identifiez et documentez vos besoins dans les domaines suivants :

  - **Fréquence des sauvegardes**     Pour plus d’informations sur les meilleures pratiques en matière de fréquence de sauvegarde, voir [Best Practices for Backup and Restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - Outils de sauvegarde **et de restauration**     Indiquez qui doit utiliser les outils et sur quels ordinateurs. Pour plus d’informations sur les outils présentés dans cette rubrique et les autorisations nécessaires, voir [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : outils et autorisations](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Emplacement**     de sauvegarde Déterminez si les sauvegardes sont conservées localement ou à distance, tout en tenant compte de la sécurité et de l’accessibilité. Spécifiez les supports à utiliser pour les sauvegardes.

  - **Configuration matérielle et logicielle requise**     Identifiez et consignez les configurations matérielle et logicielle requises spécifiques, notamment le matériel de stockage de sauvegarde et de restauration de composants spécifiques, ainsi que les logiciels et la connectivité réseau requis pour prendre en charge la sauvegarde et la restauration. Au fur et à mesure que vous développez votre configuration matérielle et logicielle requise, gardez à l’esprit les divers scénarios de restauration ci-après.

  - **Scénarios**     de restauration Voici les processus de restauration pour les scénarios suivants :
    
      - Un pool Lync Server ne fonctionne pas. Ce scénario requiert une nouvelle création de chaque serveur inclus dans le pool.
    
      - Un serveur Standard Edition Server échoue. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.
    
      - Perte du magasin central de gestion. Au minimum, ce scénario nécessite la restauration et la publication du magasin central de gestion.
    
      - Perte d’un serveur principal lorsque le magasin central de gestion fonctionne toujours normalement. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé ainsi que la restauration des bases de données.
    
      - Un serveur qui est membre d’un pool Lync Server ne fonctionne pas. Ce scénario requiert une nouvelle création du serveur sur un ordinateur nouveau ou nettoyé.
    
      - Un magasin de fichiers échoue. Ce scénario requiert la restauration du serveur de fichiers ou du cluster de fichiers.
    
      - Une base de données d’archivage, de surveillance ou de conversation permanente échoue. Ce scénario requiert une nouvelle création des bases de données et, si les données sont critiques pour l’organisation, une restauration des données. Les données d’archivage, de surveillance et de conversation permanente ne sont pas requises pour la sauvegarde et l’exécution de Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

