---
title: 'Lync Server 2013 : meilleures pratiques pour la sauvegarde et la restauration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for backup and restoration
ms:assetid: abbce0e4-973a-4624-a0c1-e0f22e1d348b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202184(v=OCS.15)
ms:contentKeyID: 51541500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dd3345545ae8c77c4ebfcece7154e91059f9aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-backup-and-restoration-for-lync-server-2013"></a>Meilleures pratiques pour la sauvegarde et la restauration pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Cette section comprend deux types de meilleures pratiques :

  - Meilleures pratiques pour la sauvegarde et la restauration.

  - Meilleures pratiques pour limiter l’impact d’un sinistre.

<div>

## <a name="best-practices-for-backup-and-restoration"></a>Meilleures pratiques de sauvegarde et restauration

Pour faciliter le processus de sauvegarde et de restauration, appliquez les meilleures pratiques suivantes lors de la sauvegarde ou de la restauration de vos données :

  - Effectuez des sauvegardes régulières, à intervalles adéquats. Le type de sauvegarde et le planning de rotation les plus simples et les plus couramment utilisés consistent à effectuer chaque nuit une sauvegarde complète de la base de données SQL Server entière. Ensuite, si la restauration est nécessaire, le processus de restauration ne nécessite qu’une seule sauvegarde et aucune donnée de jour ne doit être perdue.

  - Si vous utilisez des applets de commande ou le panneau de configuration Lync Server pour effectuer des modifications de configuration, utilisez la cmdlet **Export-CsConfiguration** pour effectuer une sauvegarde instantanée du fichier de configuration de topologie (XDS. mdf) après avoir apporté les modifications, afin de ne pas perdre les modifications si vous devez restaurer vos bases de données. Notez que cette configuration est sauvegardée au format XML et compressée sous la forme d’un fichier. ZIP.

  - Assurez-vous que le dossier partagé que vous envisagez d’utiliser pour la sauvegarde de Lync Server dispose de suffisamment d’espace disque pour contenir toutes les données sauvegardées.

  - Planifiez les sauvegardes lorsque l’utilisation de Lync Server est généralement faible, pour améliorer les performances du serveur et l’expérience utilisateur.

  - Assurez-vous que l’emplacement où vous sauvegardez les données est sécurisé (nous vous recommandons d’utiliser un emplacement distant).

  - Conservez les fichiers de sauvegarde où ils seront disponibles, au cas où vous devriez restaurer les données.

  - Planifiez et planifiez les tests périodiques des processus de restauration pris en charge par votre organisation.

  - Validez vos processus de sauvegarde et de restauration à l’avance afin de vous assurer qu’ils fonctionnent comme prévu.

</div>

<div>

## <a name="best-practices-for-minimizing-the-impact-of-a-disaster"></a>Meilleures pratiques pour limiter l’impact d’un sinistre

La meilleure stratégie pour traiter les interruptions de service désastreuses (dues à des événements non gérables, tels que des coupures de courant ou des pannes matérielles soudaines), est de supposer qu’elles se produiront et de planifier en conséquence.

Si les services Lync, avec un minimum de perturbation et de panne, sont essentiels pour l’entreprise, vous devez envisager d’implémenter des pools de serveurs frontaux couplés, comme décrit dans la rubrique [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Ensuite, si l’un de ces pools rencontre un problème, un administrateur peut faire en sorte que les utilisateurs de ce pool soient pris en charge par l’autre pool, avec un minimum de temps d’arrêt.

Les plans de gestion des sinistres que vous développez dans le cadre de votre stratégie de sauvegarde et de restauration doivent inclure les éléments suivants :

  - La mise à disposition de vos supports logiciels, ainsi que de vos logiciels et mises à jour de microprogramme, est immédiatement disponible.

  - maintenance d’enregistrements relatifs aux matériels et aux logiciels ;

  - Sauvegarde régulière de vos données et surveillance de l’intégrité de vos sauvegardes.

  - formation du personnel en matière de récupération après incident, documentation des procédures et implémentation d’exercices de simulation de récupération après sinistre ;

  - La mise à disposition de matériel de rechange ou, si vous disposez d’un contrat de niveau de service (SLA), vous devez détenir les fournisseurs de matériel et les fournisseurs pour les remplacements d’invites.

  - séparation des emplacements de vos fichiers journaux de transactions (fichiers .ldf) et des fichiers de base de données (fichiers .mdf).

</div>

</div>

<span> </span>

</div>

</div>

</div>

