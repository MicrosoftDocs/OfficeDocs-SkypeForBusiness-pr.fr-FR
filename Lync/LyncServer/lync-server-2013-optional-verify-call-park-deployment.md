---
title: 'Lync Server 2013 : (facultatif) vérification du déploiement du parcage d’appel'
description: 'Lync Server 2013 : (facultatif) vérifier le déploiement du parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541930"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="e70eb-103">Module Vérifier le déploiement du parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e70eb-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e70eb-104">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e70eb-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e70eb-105">Après avoir installé et configuré le parcage d’appel, vous devez vérifier la configuration pour vous assurer que les appels de parking et de récupération fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="e70eb-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="e70eb-106">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e70eb-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="e70eb-107">Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parkiser l’appel.</span><span class="sxs-lookup"><span data-stu-id="e70eb-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e70eb-108">Si vous avez activé le parcage d’appel dans la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui est responsable de l’appel doit se déconnecter de Lync Server, puis se reconnecter pour pouvoir voir l’option parcage d’appel dans la liste de transfert d’appel.</span><span class="sxs-lookup"><span data-stu-id="e70eb-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="e70eb-109">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="e70eb-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="e70eb-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est correctement acheminé vers la destination secondaire qui est spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="e70eb-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

