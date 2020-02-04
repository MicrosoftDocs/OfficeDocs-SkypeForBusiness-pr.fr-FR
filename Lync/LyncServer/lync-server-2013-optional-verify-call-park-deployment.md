---
title: 'Lync Server 2013 : (facultatif) vérifier le déploiement du parc d’appels'
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
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="727c9-102">Facultatif Vérifier le déploiement du parc d’appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="727c9-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="727c9-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="727c9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="727c9-104">Après l’installation et la configuration du parc d’appels, vous devez vérifier la configuration pour vous assurer que le parking et la récupération des appels fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="727c9-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="727c9-105">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="727c9-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="727c9-106">Appeler un utilisateur dont le parc d’appels est activé et demander à l’utilisateur d’appeler l’appel.</span><span class="sxs-lookup"><span data-stu-id="727c9-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="727c9-107">Si vous avez activé le parc d’appels dans la politique vocale juste avant d’effectuer ce test, l’utilisateur qui travaille en stationnement doit se déconnecter de Lync Server, puis se reconnecter pour pouvoir voir l’option de transfert d’appel dans la liste transférer l’appel.</span><span class="sxs-lookup"><span data-stu-id="727c9-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="727c9-108">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="727c9-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="727c9-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="727c9-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

