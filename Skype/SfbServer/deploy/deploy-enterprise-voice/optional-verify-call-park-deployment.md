---
title: (Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérification de votre déploiement du parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: da53d351acef3eb2fc7fcc1b59e24a83d0cb2495
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894667"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises
 
Vérification de votre déploiement du parcage d’appel dans Skype pour Business Server Enterprise Voice. 
  
Une fois que vous installez et configurez la mise en garde d’appels, vous devez vérifier la configuration pour vous assurer que le Parcage et récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parquer l’appel.
    
    > [!NOTE]
    > Si vous avez activé parcage d’appel à la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui est parcage l’appel doit vous déconnecter de Skype pour les entreprises et reconnectez-vous, pour être en mesure de voir l’option de parcage d’appel dans le transfert de liste d’appels. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.
    

