---
title: 'Lync Server 2013 : planification de l’apparence des lignes partagées'
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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planifier l’apparence des lignes partagées dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-21_

Pour plus d’informations sur la planification de l’apparence des lignes partagées dans Lync Server 2013, consultez la mise à jour cumulative 2016.

L’apparence des lignes partagées est une fonctionnalité de Lync Server 2013, mise à jour cumulative 2016 avril pour le traitement des appels multiples sur un numéro particulier appelé numéro partagé. SLA peut configurer tout utilisateur de Lync pour l’entreprise à l’aide d’un numéro partagé avec plusieurs lignes pour répondre à plusieurs appels. Les appels ne sont pas reçus réellement sur le numéro partagé, mais ils sont transférés vers les utilisateurs qui agissent en tant que délégués pour le numéro partagé. Les délégués peuvent prendre l’appel, tandis que les autres reçoivent une notification sur leur téléphone indiquant le nom de la personne qui a pris l’appel et la ligne qui est occupée. Le nombre de lignes et le nombre de délégués sont configurables pour un numéro partagé en mode partage de lignes. De plus, les options avancées, comme BusyOption (ce qui est le cas lorsque toutes les lignes sont occupées) et MissedCallOption (ce qui est le cas lorsqu’aucun des délégués ne prend d’appel), peuvent également être configurées pour un numéro partagé.

Le SLA est uniquement pris en charge sur les appareils mobiles suivants (il n’est pas pris en charge pour les clients Lync sur des ordinateurs, des téléphones mobiles ou d’autres appareils) :

  - Polycom VVX300 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX400 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX500 avec mise à jour du microprogramme 5.4.1

  - Polycom VVX600 avec mise à jour du microprogramme 5.4.1

SLA est une nouvelle fonctionnalité de Lync Server 2013, mise à jour cumulative 2016 avril.

Pour plus d’informations sur le déploiement du contrat de service d’application, voir [déploiement d’une ligne partagée dans Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Liste des fonctionnalités

La configuration d’un groupe de mode partage de lignes permet les actions suivantes :

  - Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Ces appels peuvent être basés sur RTC ou le protocole SIP.

  - Les délégués peuvent mettre en attente des appels ou les prendre.

  - Les délégués peuvent transférer des appels vers un numéro extérieur au groupe de mode partage de lignes.

  - Les délégués peuvent voir le nombre d’appels actuels sur le numéro partagé et afficher le statut de chacun de ces appels.

  - Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir comment traiter les nouveaux appels une fois cette limite atteinte. Les appels hors limite peuvent être rejetés avec une tonalité Occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.

  - Vous pouvez définir comment traiter les appels manqués (appels non pris après un certain temps). Si vous activez la messagerie vocale pour le groupe, les appels manqués sont redirigés automatiquement vers la messagerie vocale. Si vous n’avez pas activé la messagerie vocale pour le groupe (numéro partagé), vous pouvez décider de rejeter les appels manqués avec une tonalité Occupé, de les transférer vers un autre numéro ou de les déconnecter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

