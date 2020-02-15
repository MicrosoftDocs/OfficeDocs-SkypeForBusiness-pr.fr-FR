---
title: 'Lync Server 2013 : planifier l’apparence des lignes partagées'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb4f8ad407950f8d3180d030ede03a1e93cf0b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planifier l’apparence des lignes partagées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-21_

Consultez cette rubrique pour découvrir comment planifier l’apparence de ligne partagée (SLA) dans Lync Server 2013, mise à jour cumulative avril 2016.

Shared Line Appearance est une fonctionnalité de Lync Server 2013, cumulative update avril 2016 pour le traitement de plusieurs appels sur un numéro spécifique appelé « numéro partagé ». Le contrat SLA peut configurer un utilisateur Lync voix entreprise compatible avec plusieurs lignes pour répondre à plusieurs appels. Les appels ne sont pas réellement reçus sur le numéro partagé, mais ils sont transférés aux utilisateurs qui agissent en tant que délégués pour le numéro partagé. Tous les délégués peuvent sélectionner l’appel pendant que le reste des délégués obtient une notification sur leur téléphone indiquant qui a pris l’appel et quelle ligne a été utilisée comme résultat. Le nombre de lignes et les délégués peuvent être configurés pour un numéro partagé dans le contrat SLA. De plus, les options avancées, telles que BusyOption (ce qui se passe dans une situation où toutes les lignes sont occupées) et MissedCallOption (le cas dans lequel aucun des délégués ne récupère un appel), peuvent également être configurées pour un numéro partagé.

Le contrat SLA est pris en charge uniquement sur les appareils téléphoniques suivants (il n’est pas pris en charge pour les clients Lync sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :

  - Polycom VVX300 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX400 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX500 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX600 avec mise à jour du microprogramme 5.4.1

Le contrat SLA est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative avril 2016.

Pour plus d’informations sur le déploiement du contrat SLA, voir [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Liste des fonctionnalités

La configuration d’un groupe de SLA permet d’activer les éléments suivants :

  - Tous les délégués du groupe peuvent répondre à des appels entrants vers le même numéro partagé. Les appels peuvent être basés sur PSTN ou sur SIP.

  - Les délégués peuvent suspendre et reprendre des appels.

  - Les délégués peuvent transférer des appels vers un numéro en dehors du groupe SLA.

  - Les délégués peuvent voir le nombre d’appels actuellement sur le numéro partagé et afficher l’état de chacun de ces appels.

  - Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir la façon dont vous souhaitez que les appels supplémentaires soient gérés une fois ce maximum atteint. Les appels excédentaires peuvent être rejetés avec un signal occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.

  - Vous pouvez configurer le mode de traitement des appels manqués (appels non récupérés après un certain temps). Si vous activez la messagerie vocale pour l’identité du groupe, les appels manqués sont automatiquement dirigés vers la messagerie vocale. Si la messagerie vocale n’est pas activée pour l’identité du groupe (numéro partagé), vous pouvez choisir de refuser les appels manqués à l’aide d’un signal d’occupation, de le transférer à un autre numéro ou de le déconnecter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

