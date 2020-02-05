---
title: Vérifier les règles de normalisation du parc d’appels dans Skype entreprise
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: En savoir plus sur les règles de normalisation du parc d’appels dans Skype entreprise Server Voice.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766887"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Vérifier les règles de normalisation du parc d’appels dans Skype entreprise
 
En savoir plus sur les règles de normalisation du parc d’appels dans Skype entreprise Server Voice.
  
Le parking des orbites ne doit pas être normalisé. Vérifiez dans vos plans de numérotation que vos numéros orbites ne sont pas normalisés. Si vous devez créer une règle de normalisation supplémentaire pour empêcher la normalisation de vos orbites, suivez la procédure décrite dans la rubrique [créer ou modifier un plan de numérotation dans Skype entreprise Server](dial-plans.md) pour définir une nouvelle règle de normalisation, de sorte que le **modèle à faire correspondre** identifie la plage d’orbite et le **modèle de translation** est **$1**. Par exemple, si la plage de votre stationnement d’appels est 7000-7999, le **modèle à faire correspondre** est **^ ({3}7 \ d) $** et le **modèle de traduction** est **$1**.
  
> [!IMPORTANT]
> Vérifiez que la règle de normalisation par défaut de vos plans de numérotation ne contient pas **^\*(\d)**. Dans le cas contraire, votre règle de normalisation de parc d’appels ne sera jamais exécutée.
  
## <a name="see-also"></a>Voir aussi

[Création ou modification d’un plan de numérotation dans Skype entreprise Server](dial-plans.md)

