---
title: Vérifier les règles de normalisation pour le parcier d’appel dans Skype Entreprise
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: En savoir plus sur les règles de normalisation pour le parcier d’appel dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830574"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Vérifier les règles de normalisation pour le parcier d’appel dans Skype Entreprise
 
En savoir plus sur les règles de normalisation pour le parcier d’appel dans Skype Entreprise Server Voix Entreprise.
  
Les orbites de parcier d’appel ne doivent pas être normalisées. Vérifiez vos plans de numérotation pour vous assurer que vos numéros d’orbite ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure de création ou de modification d’un plan de numérotation dans Skype Entreprise [Server](dial-plans.md) pour définir une nouvelle règle de normalisation, afin que le modèle à suivre **identifie** la plage d’orbites et que le modèle de traduction soit **de 1 $**.  Par exemple, si votre plage d’orbites de parc automatique est  de 7 000 à  7 999, le modèle à suivre est **^(7\d {3} )$** et le modèle de traduction est **de 1 $**.
  
> [!IMPORTANT]
> Assurez-vous que la règle de normalisation par défaut dans vos plans de numérotation ne contient **pas ^(\d \* )**. Dans le cas contraire, votre règle de normalisation du parc d’appel ne s’exécutera jamais.
  
## <a name="see-also"></a>Voir aussi

[Créer ou modifier un plan de numérotation dans Skype Entreprise Server](dial-plans.md)

