---
title: Vérifier les règles de normalisation pour le parc Skype Entreprise
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: En savoir plus sur les règles de normalisation pour le parc Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 35ffdfd6fe7e4289ebb4fa0ecd6cef9a26256bb0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404356"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Vérifier les règles de normalisation pour le parc Skype Entreprise
 
En savoir plus sur les règles de normalisation pour le parc Skype Entreprise Server Voix Entreprise.
  
Les orbites de parcier d’appel ne doivent pas être normalisées. Vérifiez vos plans de numérotation pour vous assurer que vos numéros d’orbite ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure de création ou de modification d’un plan de numérotation dans [Skype Entreprise Server](dial-plans.md) pour définir une nouvelle règle de normalisation, afin que le modèle à **suivre identifie la** plage d’orbites et que le modèle de traduction soit  **de 1 $**. Par exemple, si votre plage d’orbites de parcier d’appel est de 7 000 à  7 999, le modèle à suivre est **^(7\d{3})$** et le modèle de traduction est **de 1 $**.
  
> [!IMPORTANT]
> Assurez-vous que la règle de normalisation par défaut dans vos plans de numérotation ne contient **pas ^(\d\*)**. Dans le cas contraire, votre règle de normalisation du parc d’appel ne s’exécutera jamais.
  
## <a name="see-also"></a>Voir aussi

[Créer ou modifier un plan de numérotation dans Skype Entreprise Server](dial-plans.md)

