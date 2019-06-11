---
title: 'Lync Server 2013: meilleures pratiques pour la sauvegarde et la restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc7a926bd8fd5c61f87d5e8252c30f40e5a6a69
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Recommandations en matière de sauvegarde et de restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Cette section inclut deux types de meilleures pratiques:

  - Pratiques recommandées pour la sauvegarde et la restauration.

  - Recommandations permettant de réduire l’impact d’un sinistre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Recommandations en matière de sauvegarde et de restauration

Pour faciliter votre processus de sauvegarde et de restauration, appliquez les meilleures pratiques suivantes lors de la sauvegarde ou de la restauration de vos données:

  - Effectuez des sauvegardes régulières à intervalles appropriés. Le plus simple et le plus souvent utilisé dans les plannings de type et de rotation est une sauvegarde complète et nocturne de l’ensemble de la base de données SQL Server. Si une restauration est nécessaire, le processus de restauration ne nécessite qu’une seule sauvegarde et aucune donnée de jour ne doit être perdue.

  - Si vous utilisez des cmdlets ou le panneau de configuration de Lync Server pour apporter des modifications de configuration, utilisez l’applet de commande **Export-CsConfiguration** pour effectuer une sauvegarde de capture instantanée du fichier de configuration de la topologie (XDS. mdf) après avoir effectué les modifications, afin de ne pas perdre les modifications si vous devez restaurer vos bases de données. Notez que cette configuration est sauvegardée au format XML et compactée sous forme de fichier ZIP.

  - Assurez-vous que le dossier partagé que vous envisagez d’utiliser pour la sauvegarde de Lync Server dispose de suffisamment d’espace disque pour contenir toutes les données sauvegardées.

  - Planifier des sauvegardes lorsque la consommation de Lync Server est généralement faible, afin d’améliorer les performances du serveur et l’interface utilisateur.

  - Assurez-vous que l’emplacement de sauvegarde des données est sécurisé (nous vous recommandons d’utiliser un emplacement distant).

  - Conservez les fichiers de sauvegarde dans lesquels ils seront disponibles, si vous avez besoin de restaurer les données.

  - Planifiez et planifiez des tests périodiques des processus de restauration pris en charge par votre organisation.

  - Validez vos processus de sauvegarde et de restauration à l’avance pour vérifier qu’ils fonctionnent comme prévu.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Recommandations pour réduire l’impact d’un sinistre

La meilleure stratégie pour gérer les interruptions de service désastreuses (provoquées par des événements ingérables tels que les coupures de courant ou les défaillances matérielles soudaines) est de supposer qu’elles se produiront et de planifier en conséquence.

Si les services Lync, présentant un minimum de perturbation et d’interruption de service, sont vitaux pour votre organisation, il est recommandé de mettre en œuvre des pools de serveurs frontaux couplés, comme décrit dans la section [planification de la haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Ensuite, si l’une de ces réserves rencontre un problème, un administrateur peut basculer les utilisateurs de ce pool pour qu’ils soient desservis par l’autre réserve, avec un minimum de temps d’arrêt.

Les plans de gestion des sinistres développés dans le cadre de votre stratégie de sauvegarde et de restauration doivent inclure les éléments suivants:

  - La conservation de votre média logiciel ainsi que des mises à jour de logiciels et de microprogrammes, facilement disponibles.

  - Maintenance des enregistrements matériels et logiciels.

  - Sauvegarder vos données régulièrement et surveiller l’intégrité de vos sauvegardes.

  - Formation de votre équipe dans le cas d’une reprise après sinistre, de procédures de documentation et de l’implémentation de perçages de simulation de récupération d’urgence.

  - La conservation de matériel de réserve ou, si vous disposez d’un contrat de niveau de service (SLA), un contrat avec des fournisseurs de matériel et des fournisseurs pour les remplacements d’instructions.

  - Séparation de l’emplacement de vos fichiers journaux de transactions (fichiers. ldf) et fichiers de base de données (fichiers. mdf).

</div>

</div>

<span> </span>

</div>

</div>

</div>

