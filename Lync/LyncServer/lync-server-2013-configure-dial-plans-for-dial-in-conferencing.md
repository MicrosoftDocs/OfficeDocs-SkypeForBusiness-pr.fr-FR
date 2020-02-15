---
title: 'Lync Server 2013 : configuration des plans de numérotation pour les conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28dd2ddb0633a45d19f1a7bb7638d86e042658b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Veillez à ce qu’au moins une règle de normalisation dans chaque plan convertisse les numéros de poste en numéros de téléphone complets au format E.164. Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir des postes en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.

Pour configurer des plans de numérotation pour la conférence rendez-vous, procédez comme suit :

  - Si vous déployez voix entreprise ou non, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et vous assurer qu’une règle de normalisation convertit correctement vos numéros d’accès entrant. Pour obtenir des instructions détaillées, consultez [la rubrique modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si vous n’avez pas déployé voix entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous. Veillez à inclure une région de conférence rendez-vous. Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si vous avez déployé voix entreprise, modifiez les plans de numérotation de voix entreprise selon vos besoins pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, consultez [la rubrique modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Pour plus d’informations sur la planification des régions, voir Configuration requise pour les conférences rendez [-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Afficher les informations de plan de numérotation dans Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Création d’un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

