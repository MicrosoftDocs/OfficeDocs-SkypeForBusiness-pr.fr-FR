---
title: (Facultatif) Vérifier le déploiement du parcement d’appel dans Skype Entreprise
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérification de votre déploiement du parcage d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 28079ff0db27319ee1dc8c93e2e3509173d4c68e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62403458"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Facultatif) Vérifier le déploiement du parcement d’appel dans Skype Entreprise
 
Vérification de votre déploiement du parcage d’appel dans Skype Entreprise Server Voix Entreprise. 
  
Après avoir installé et configuré le parcage d’appel, vous devez vérifier la configuration pour vous assurer que le parcage et la récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appelez un utilisateur pour qui le parc d’appel est activé et l’utilisateur pare l’appel.
    
    > [!NOTE]
    > Si vous avez activé le parcage d’appel dans la stratégie de voix juste avant d’effectuer ce test, l’utilisateur qui parque l’appel doit se connecter à Skype Entreprise, puis se connecter à nouveau, pour pouvoir voir l’option Parcage d’appel dans la liste des appels de transfert. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est correctement acheminé vers la destination secondaire qui est spécifiée pour **OnTimeoutURI**.
    

