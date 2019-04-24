---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir un nom de domaine complet du pool Applications approuvées (FQDN), spécifiez les éléments suivants :'
ms.openlocfilehash: 12ea56f285dfffbe78b74c8eece8211a8676333e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202095"
---
# <a name="add-trusted-application-pool-fqdn"></a>Ajouter un nom de domaine complet du pool d’applications approuvées
 
Pour définir un nom de domaine complet du pool Applications approuvées (FQDN), spécifiez les éléments suivants :
  
Nom de domaine complet du serveur ou du pool de serveurs qui hébergent les applications approuvées.
  
Sélectionnez le **pool de plusieurs ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées à partir de l’équilibrage de charge et une haute disponibilité ou sélectionnez le **pool à ordinateur unique** si vous n’avez pas besoin de charger équilibrage ou haute disponibilité.
  
> [!IMPORTANT]
> Un seul serveur d’Applications approuvées ne peut pas être converti en un pool de serveurs ultérieurement. Si vous pensez que vous devrez peut-être un pool à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur maintenant et ajouter des serveurs cas. 
  
Pour plus d’informations sur les pools d’Applications approuvées, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

