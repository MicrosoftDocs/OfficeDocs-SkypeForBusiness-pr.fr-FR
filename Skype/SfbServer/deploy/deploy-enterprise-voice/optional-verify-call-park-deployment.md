---
title: Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Vérifier votre déploiement du parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292842"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Facultatif Vérifier le déploiement du parc d’appels dans Skype entreprise
 
Vérifier votre déploiement du parc d’appels dans Skype entreprise Server Voice. 
  
Après l’installation et la configuration du parc d’appels, vous devez vérifier la configuration pour vous assurer que le parking et la récupération des appels fonctionnent comme prévu. Vérifiez au minimum les éléments suivants :
  
- Appeler un utilisateur dont le parc d’appels est activé et demander à l’utilisateur d’appeler l’appel.
    
    > [!NOTE]
    > Si vous avez activé le parc d’appels dans la politique vocale avant d’effectuer ce test, l’utilisateur qui travaille en stationnement doit se déconnecter de Skype entreprise, puis se reconnecter pour pouvoir voir l’option de transfert d’appel dans la liste transférer l’appel. 
  
- Composez le numéro orbite pour récupérer l’appel.
    
- Parquez un autre appel, laissez expirer le délai d’attente de l’appel parqué et ne décrochez pas lors du rappel. Vérifiez que l’appel dont le délai d’attente a expiré est routé correctement vers la destination secondaire spécifiée pour **OnTimeoutURI**.
    

