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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise
 
Vérifier votre déploiement du parc d’appels dans Skype entreprise Server Voice. 
  
Après l’installation et la configuration du parc d’appels, vous devez vérifier la configuration pour vous assurer que le parking et la récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appeler un utilisateur dont le parc d’appels est activé et demander à l’utilisateur d’appeler l’appel.
    
    > [!NOTE]
    > Si vous avez activé le parc d’appels dans la politique vocale avant d’effectuer ce test, l’utilisateur qui travaille en stationnement doit se déconnecter de Skype entreprise, puis se reconnecter pour pouvoir voir l’option de transfert d’appel dans la liste transférer l’appel. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.
    

