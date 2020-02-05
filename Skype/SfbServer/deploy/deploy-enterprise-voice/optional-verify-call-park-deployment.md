---
title: Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérifier votre déploiement du parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767337"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="a452a-103">Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a452a-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="a452a-104">Vérifier votre déploiement du parc d’appels dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="a452a-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a452a-105">Après l’installation et la configuration du parc d’appels, vous devez vérifier la configuration pour vous assurer que le parking et la récupération des appels fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="a452a-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="a452a-106">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a452a-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="a452a-107">Appeler un utilisateur dont le parc d’appels est activé et demander à l’utilisateur d’appeler l’appel.</span><span class="sxs-lookup"><span data-stu-id="a452a-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a452a-108">Si vous avez activé le parc d’appels dans la politique vocale avant d’effectuer ce test, l’utilisateur qui travaille en stationnement doit se déconnecter de Skype entreprise, puis se reconnecter pour pouvoir voir l’option de transfert d’appel dans la liste transférer l’appel.</span><span class="sxs-lookup"><span data-stu-id="a452a-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="a452a-109">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="a452a-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="a452a-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="a452a-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

