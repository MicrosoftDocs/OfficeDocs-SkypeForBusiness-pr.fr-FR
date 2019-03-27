---
title: (Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérification de votre déploiement du parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 514c82590d56a2de16ca31cc892032afe5e7a34c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895096"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="24537-103">(Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="24537-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="24537-104">Vérification de votre déploiement du parcage d’appel dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="24537-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="24537-105">Une fois que vous installez et configurez la mise en garde d’appels, vous devez vérifier la configuration pour vous assurer que le Parcage et récupération des appels fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="24537-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="24537-106">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="24537-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="24537-107">Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parquer l’appel.</span><span class="sxs-lookup"><span data-stu-id="24537-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="24537-108">Si vous avez activé parcage d’appel à la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui est parcage l’appel doit vous déconnecter de Skype pour les entreprises et reconnectez-vous, pour être en mesure de voir l’option de parcage d’appel dans le transfert de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="24537-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="24537-109">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="24537-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="24537-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="24537-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

