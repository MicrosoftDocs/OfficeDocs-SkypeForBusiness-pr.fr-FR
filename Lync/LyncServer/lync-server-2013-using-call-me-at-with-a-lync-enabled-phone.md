---
title: 'Lync Server 2013 : utilisation de m’appeler avec un téléphone compatible Lync'
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
ms.openlocfilehash: 1d4b117970cec1e40b4d18928f82bc0cf2831eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Utiliser appeler avec un téléphone compatible Lync et Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-08-09_

La fonctionnalité m’appeler au niveau de Lync permet aux utilisateurs d’accéder à la partie audio d’une conférence en utilisant un téléphone mobile, « ligne fixe » ou tout autre appareil connecté au réseau téléphonique public commuté (RTC). Lorsque vous essayez de participer à une réunion à l’aide de Lync, la boîte de dialogue **accéder** à la partie audio de la réunion s’affiche.

![Capture d’écran de la fenêtre de connexion audio de la réunion à l’aide de Lync](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Capture d’écran de la fenêtre de connexion audio de la réunion à l’aide de Lync")

Si vous sélectionnez **m’appeler au**, vous pouvez sélectionner un numéro de téléphone dans la liste déroulante. Lync Server 2013 effectue un appel téléphonique au numéro sélectionné et vous pouvez l’utiliser pour participer à la partie audio de la Conférence.

La liste déroulante est renseignée en fonction des numéros de téléphone (téléphone mobile, téléphone personnel ou autre téléphone) que vous avez entrés sous l’onglet **téléphones** dans la boîte de dialogue **Lync – options** :

![Capture d’écran des options de configuration des téléphones Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Capture d’écran des options de configuration des téléphones Lync")

Si vous n’avez pas entré de numéro de téléphone dans l’onglet **téléphones** , aucun numéro n’est disponible dans la liste déroulante. Toutefois, vous pouvez toujours cliquer sur **nouveau numéro** et faire en sorte que Lync Server appelle le numéro de téléphone de votre choix :

![Capture d’écran de la fenêtre de l’appel audio de réunion Lync](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Capture d’écran de la fenêtre de l’appel audio de réunion Lync")

La fonction m’appeler au-moi fonctionne très bien si vous l’utilisez comme prévu : en utilisant Lync Server pour appeler un numéro de téléphone PSTN. Néanmoins, vous pouvez effectuer une mise à niveau plus lente si vous demandez à Lync Server de vous appeler auprès d’un point de terminaison Lync (par exemple, un téléphone dans une salle de conférence). Vous trouverez ci-après le problème que vous pourriez rencontrer, ainsi que deux méthodes pour contourner le problème.

Pour commencer, voici ce qui se produit lorsque vous fournissez la fonction m’appeler au numéro de téléphone d’un téléphone compatible Lync. Supposez que Ken Myer tente de participer à une réunion en ayant appelé le serveur Lync sur 1-206-555-1219, un numéro de Téléphone Lync Server. Ken sera initialement connecté à la réunion, mais après quelques secondes, Lync affichera le message n' **a pas été terminé ou a pris fin**, et Ken aura été rejeté de la réunion :

![Capture d’écran de la fenêtre de conférence d’appels Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Capture d’écran de la fenêtre de conférence d’appels Lync")

Notez toutefois qu’il existe une divergence dans la fenêtre de conversation de Lync. Ken Myer est le seul nom indiqué sous le titre **participants** . Toutefois, si vous regardez dans la barre de titre de la fenêtre, vous verrez que la Conférence comporte au total 4 participants.

De même, si vous regardez dans la fenêtre de conversation de n’importe quel participant à la Conférence, vous ne verrez pas Ken Myer en tout lieu :

![Capture d’écran de la fenêtre Liste des participants Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Capture d’écran de la fenêtre Liste des participants Lync")

Pour l’instant, Ken Myer sera en mesure de participer à la partie audio de l’appel à l’aide de son téléphone compatible Lync. La fonction m’appeler au moment de l’appel a réellement fonctionné, mais le niveau d’expérience utilisateur est inférieur à la taille optimale.

Il existe au moins deux moyens de contourner ce problème. Si vous avez déjà rejoint une conférence de cette manière (comme Ken Myer), vous pouvez généralement résoudre le problème en effectuant une autre modalité. Par exemple, si vous envoyez un message instantané, la fenêtre de conversation montre alors tous les participants à la Conférence, y compris vous-même :

![Capture d’écran de la liste des participants et des conversations Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Capture d’écran de la liste des participants et des conversations Lync")

À ce stade, vous devriez être en mesure de participer à la réunion de la manière attendue.

Vous pouvez aussi éviter ce problème en modifiant la façon dont vous rejoignez la réunion. Si vous avez besoin que Lync Server appelle un téléphone compatible Lync Server, vous devez commencer par rejoindre la réunion sans connexion audio. Pour ce faire, sélectionnez ne pas participer au système audio lorsque la boîte de dialogue accéder à la partie audio de la réunion apparaît :

![Capture d’écran de la fenêtre ne pas participer à la réunion audio dans Lync](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Capture d’écran de la fenêtre ne pas participer à la réunion audio dans Lync")

Une fois que vous avez réussi à vous connecter à la réunion, vous pouvez désormais « inviter » le téléphone compatible Lync Server à rejoindre la réunion. Pour cela, placez le pointeur de la souris sur l’icône personnes, puis cliquez sur **inviter d’autres personnes**:

![Capture d’écran de la fenêtre inviter d’autres participants à Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Capture d’écran de la fenêtre inviter d’autres participants à Lync")

La boîte de dialogue **Envoyer un message instantané** s’affiche. Ignorez le titre de la boîte de dialogue (vous n’envoyez pas de message instantané) et tapez le numéro de téléphone du téléphone compatible Lync :

![Capture d’écran de la boîte de dialogue Envoyer un message instantané](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Capture d’écran de la boîte de dialogue Envoyer un message instantané")

Lorsque vous cliquez sur **OK**, Lync Server appelle le numéro entré dans la boîte de dialogue. Une fois la connexion établie, vous bénéficierez des fonctionnalités audio complètes par le biais du téléphone compatible Lync et vous pourrez voir et utiliser la liste complète de la Conférence.

</div>

<span> </span>

</div>

</div>

</div>

