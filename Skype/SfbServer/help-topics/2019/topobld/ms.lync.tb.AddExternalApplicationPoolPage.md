---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir un nom de domaine complet (FQDN) du pool d’applications approuvé, spécifiez les éléments suivants :'
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787734"
---
# <a name="add-trusted-application-pool-fqdn"></a>Ajouter un nom de domaine complet du pool d’applications approuvées
 
Pour définir un nom de domaine complet (FQDN) du pool d’applications approuvé, spécifiez les éléments suivants :
  
Nom de domaine complet du serveur ou du pool de serveurs qui hébergeront les applications approuvées.
  
Sélectionner **plusieurs pools d’ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées d’équilibrage de charge et de haute disponibilité, **ou si vous** n’avez pas besoin d’équilibrage de charge ou de haute disponibilité.
  
> [!IMPORTANT]
> Un serveur d’applications de confiance unique ne peut pas être converti en pool de serveurs ultérieurement. Si vous pensez que vous aurez peut-être besoin d’un regroupement à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur et ajouter des serveurs si nécessaire. 
  
Pour plus d’informations sur les pools d’applications de confiance, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

