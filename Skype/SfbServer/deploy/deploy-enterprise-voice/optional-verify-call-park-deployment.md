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
# <a name="optional-verify-call-park-deployment-in-skype-for-business-2015"></a>(Facultatif) Vérification du déploiement du parcage d’appel dans Skype Entreprise 2015
 
Vérification de votre déploiement de parc d’appel dans Skype pour Business Server Voix Entreprise. 
  
Une fois que vous installez et configurez le parc de l’appel, vous devez vérifier la configuration pour vous assurer que le stationnement et la récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appeler un utilisateur qui possède le parc d’appel activé et le parc de l’utilisateur l’appel.
    
    > [!NOTE]
    > Si vous avez activé le parc de l’appel dans une stratégie voice juste avant l’exécution de ce test, l’utilisateur qui est l’appel de stationnement doit se déconnecter de Skype pour les entreprises et vous connecter de nouveau, pour être en mesure de voir l’option appel Park dans le transfert de liste d’appels. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.
    

