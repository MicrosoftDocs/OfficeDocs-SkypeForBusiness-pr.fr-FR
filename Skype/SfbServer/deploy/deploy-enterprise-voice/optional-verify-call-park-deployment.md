---
title: (Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises
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
ms.openlocfilehash: b07b3b3bfb709770a4f30f2f6cb43e5ce5dbcc3a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000528"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Facultatif) Vérifier le déploiement de parcage d’appel dans Skype pour les entreprises
 
Vérification de votre déploiement du parcage d’appel dans Skype pour Business Server Enterprise Voice. 
  
Une fois que vous installez et configurez la mise en garde d’appels, vous devez vérifier la configuration pour vous assurer que le Parcage et récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appelez un utilisateur qui a activé le parcage d’appel et demandez-lui de parquer l’appel.
    
    > [!NOTE]
    > Si vous avez activé parcage d’appel à la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui est parcage l’appel doit vous déconnecter de Skype pour les entreprises et reconnectez-vous, pour être en mesure de voir l’option de parcage d’appel dans le transfert de liste d’appels. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.
    

