---
title: 'Lync Server 2013 : Configuration des plans de numérotation pour les conférences rendez-vous'
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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a>Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-25_

Lorsque vous déployez la conférence rendez-vous, vous devez créer ou modifier un ou plusieurs plans de routage des numéros de téléphone d’accès entrant. Vérifiez qu’au moins une règle de normalisation dans chaque plan de numérotation convertit les extensions de téléphone en numéros de téléphone valides au format E. 164. Les utilisateurs de conférences rendez-vous participent à des conférences en tant qu’utilisateurs d’entreprise authentifiés en entrant leur code confidentiel et leur numéro de téléphone. Vous avez besoin d’une règle de normalisation pour convertir les numéros de poste en numéros de téléphone complets afin que les utilisateurs puissent être authentifiés lorsqu’ils saisissent simplement un numéro de poste.

Pour configurer des plans de numérotation pour la Conférence rendez-vous, procédez comme suit :

  - Que vous déployiez ou non Voix Entreprise, modifiez le plan de numérotation global pour ajouter une région de conférence rendez-vous et veillez à ce qu’une règle de normalisation convertisse avec précision vos numéros d’accès. Pour obtenir des instructions détaillées, voir [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

  - Si vous n’avez pas déployé Voix Entreprise, créez des plans de numérotation pour vos numéros d’accès aux conférences rendez-vous. Veillez à inclure une région de conférence rendez-vous. Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

  - Si vous avez déployé Voix Entreprise, modifiez, si nécessaire, les plans de numérotation de Voix Entreprise pour inclure des régions et utilisez les règles de normalisation appropriées pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, voir [modifier un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md). Vous pouvez également créer des plans de numérotation dédiés, utilisés exclusivement pour les numéros d’accès entrant. Pour obtenir des instructions détaillées, voir [créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md).

Pour plus d’informations sur les régions de planification, voir [exigences relatives aux conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Afficher les informations de plan de numérotation dans Lync Server 2013](lync-server-2013-view-dial-plan-information.md)

  - [Créer un plan de numérotation dans Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

  - [Modification d’un plan de numérotation dans Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

  - [Définition de règles de normalisation dans Lync Server 2013](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

