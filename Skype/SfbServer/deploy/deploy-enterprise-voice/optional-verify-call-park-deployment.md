---
title: (Facultatif) Vérification du déploiement du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérification de votre déploiement de parc d’appel dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: e8b3b0abd06ab8dc69bbe1fbcc5f091dd1350966
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a><span data-ttu-id="ecdc9-103">(Facultatif) Vérification du déploiement du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="ecdc9-103">(Optional) Verify Call Park deployment in Skype for Business 2015</span></span>
 
<span data-ttu-id="ecdc9-104">Vérification de votre déploiement de parc d’appel dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ecdc9-105">Une fois que vous installez et configurez le parc de l’appel, vous devez vérifier la configuration pour vous assurer que le stationnement et la récupération des appels fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="ecdc9-106">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ecdc9-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="ecdc9-107">Appeler un utilisateur qui possède le parc d’appel activé et le parc de l’utilisateur l’appel.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ecdc9-108">Si vous avez activé le parc de l’appel dans une stratégie voice juste avant l’exécution de ce test, l’utilisateur qui est l’appel de stationnement doit se déconnecter de Skype pour les entreprises et vous connecter de nouveau, pour être en mesure de voir l’option appel Park dans le transfert de liste d’appels.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="ecdc9-109">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="ecdc9-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="ecdc9-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

