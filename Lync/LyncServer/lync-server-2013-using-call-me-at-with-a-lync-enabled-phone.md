---
title: 'Lync Server 2013 : utilisation de m’appeler à l’aide d’un téléphone compatible Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c91980655d6786a092856c454ce4d662fef56e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Utilisation de m’appeler à l’aide d’un téléphone compatible Lync et de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-08-09_

La fonctionnalité m’appeler dans Lync permet aux utilisateurs de rejoindre la partie audio d’une conférence à l’aide d’un téléphone cellulaire, d’une ligne fixe ou d’un autre appareil connecté au réseau téléphonique commuté (PSTN). Lorsque vous tentez de participer à une réunion à l’aide de Lync, vous verrez généralement apparaître la boîte de dialogue **audio joindre une réunion** :

![Capture d’écran de la capture de la fenêtre audio de la réunion](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Capture d’écran de la capture de la fenêtre audio de la réunion")

Si vous sélectionnez **m’appeler au**, vous pouvez choisir un numéro de téléphone dans la liste déroulante. Lync Server 2013 passe un appel téléphonique au numéro sélectionné et vous pouvez ensuite utiliser ce téléphone pour participer à la partie audio de la Conférence.

La liste déroulante est complétée par les numéros de téléphone (pour le téléphone mobile, téléphone personnel ou autre téléphone) que vous avez entrés sous l’onglet **téléphones** de la boîte de dialogue **Lync-options** :

![Capture d’écran des options de configuration des téléphones Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Capture d’écran des options de configuration des téléphones Lync")

Si vous n’avez pas entré de numéros de téléphone dans l’onglet **téléphones** , aucun numéro n’est disponible dans la zone de liste déroulante. Toutefois, vous pouvez toujours cliquer sur **nouveau numéro** et faire en sorte que Lync Server compose le numéro de votre choix :

![Capture d’écran de la fenêtre Lync Join Meeting audio Calling](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Capture d’écran de la fenêtre Lync Join Meeting audio Calling")

La fonctionnalité m’appeler sur fonctionne extrêmement bien si vous l’utilisez dans la mesure où elle a été conçue : en faisant appel à Lync Server pour appeler un numéro de téléphone PSTN. Toutefois, vous pouvez rencontrer une expérience moins efficace que si vous demandez à Lync Server de vous appeler auprès d’un point de terminaison compatible Lync (par exemple, un téléphone dans une salle de conférence). Vous trouverez ci-dessous le problème que vous pouvez rencontrer, ainsi que deux façons de contourner le problème.

Pour commencer, voici ce qui se passe lorsque vous fournissez la fonctionnalité me contacter avec le numéro de téléphone d’un téléphone compatible Lync. Supposons que Ken Myer tente de participer à une réunion en faisant appel à Lync Server de la part de 1-206-555-1219, un numéro de téléphone compatible Lync Server. Ken est initialement connecté à la réunion, mais après quelques secondes, l’appel du message **n’a pas abouti ou s’est terminé**, et Ken a été supprimé de la réunion :

![Capture d’écran de la fenêtre Conférence d’appels Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Capture d’écran de la fenêtre Conférence d’appels Lync")

Notez cependant qu’il existe une incohérence dans la fenêtre de conversation Lync. Ken Myer est le seul nom figurant sous l’en-tête **participants** . Toutefois, si vous regardez dans la barre de titre de la fenêtre, vous verrez que la conférence contient au total 4 participants.

De même, si vous regardez dans la fenêtre de conversation de l’un des autres participants de la Conférence, vous ne verrez pas Ken Myer dans la section :

![Capture d’écran de la fenêtre Liste des participants Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Capture d’écran de la fenêtre Liste des participants Lync")

En même temps, Ken Myer pourra participer à la partie audio de l’appel à l’aide de son téléphone compatible Lync. La fonctionnalité m’appeler sur a réellement fonctionné, mais l’expérience utilisateur n’est pas optimale.

Il existe au moins deux façons de contourner ce problème. Si vous avez déjà rejoint une conférence de cette manière (par exemple, Ken Myer), vous pouvez généralement résoudre le problème en effectuant une autre modalité. Par exemple, si vous envoyez un message instantané, la fenêtre de conversation affiche désormais tous les participants à la Conférence, y compris vous-même :

![Capture d’écran de la liste des participants et conversations Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Capture d’écran de la liste des participants et conversations Lync")

À ce stade, vous devriez être en mesure de participer à la réunion de la manière attendue.

Vous pouvez également éviter ce problème en modifiant la façon dont vous rejoignez la réunion. Si vous devez faire en sorte que Lync Server appelle un téléphone compatible Lync Server, vous devez commencer par rejoindre la réunion sans connexion audio. Pour ce faire, sélectionnez ne pas participer au signal audio lorsque vous y êtes invité dans la boîte de dialogue audio joindre la réunion :

![Capture d’écran de la fenêtre de l’audio de la réunion](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Capture d’écran de la fenêtre de l’audio de la réunion")

Une fois que vous avez réussi à vous connecter à la réunion, vous pouvez désormais « inviter » le téléphone compatible Lync Server à participer à la réunion. Pour ce faire, placez le curseur de la souris sur l’icône contacts, puis cliquez sur **inviter d’autres personnes**:

![Capture d’écran de la fenêtre inviter d’autres participants sur Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Capture d’écran de la fenêtre inviter d’autres participants sur Lync")

La boîte de dialogue **Envoyer un message instantané** s’affiche. Ignorez le titre de la boîte de dialogue (vous n’envoyez pas réellement un message instantané) et tapez le numéro de téléphone du téléphone compatible Lync :

![Capture d’écran de la boîte de dialogue Envoyer un message instantané](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Capture d’écran de la boîte de dialogue Envoyer un message instantané")

Une fois que vous avez cliqué sur **OK**, Lync Server appellera le numéro entré dans la boîte de dialogue. Une fois la connexion établie, vous bénéficierez de toutes les fonctionnalités audio via le téléphone compatible Lync et vous pourrez voir et interagir avec la liste complète des conférences.

</div>

<span> </span>

</div>

</div>

</div>

