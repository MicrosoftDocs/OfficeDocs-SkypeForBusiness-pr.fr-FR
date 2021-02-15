---
title: (Facultatif) Vérifier le déploiement du parcement d’appel dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérification de votre déploiement du parcage d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830894"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="a2ea6-103">(Facultatif) Vérifier le déploiement du parcement d’appel dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a2ea6-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="a2ea6-104">Vérification de votre déploiement du parcage d’appel dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="a2ea6-105">Après avoir installé et configuré le parcage d’appel, vous devez vérifier la configuration pour vous assurer que le parcage et la récupération des appels fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="a2ea6-106">Vérifiez au minimum les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a2ea6-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="a2ea6-107">Appelez un utilisateur pour qui le parc d’appel est activé et l’utilisateur pare l’appel.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a2ea6-108">Si vous avez activé le parcage d’appel dans la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui parque l’appel doit se connecter à Skype Entreprise, puis se connecter à nouveau, pour pouvoir voir l’option Parcage d’appel dans la liste des appels de transfert.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="a2ea6-109">Composez le numéro orbite pour récupérer l’appel.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="a2ea6-p102">Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est correctement acheminé vers la destination secondaire qui est spécifiée pour **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="a2ea6-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

