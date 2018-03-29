---
title: Ajouter un Pool d’Application de confiance nom de domaine complet
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Pour définir un nom de domaine complet du pool Applications sécurisées (FQDN), spécifiez les éléments suivants :'
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-trusted-application-pool-fqdn"></a>Ajouter un Pool d’Application de confiance nom de domaine complet
 
Pour définir un nom de domaine complet du pool Applications sécurisées (FQDN), spécifiez les éléments suivants :
  
Un nom de domaine complet du serveur ou du pool de serveurs qui hébergeront les applications approuvées.
  
Sélectionnez le **pool d’ordinateur plusieurs** si vous déployez un pool de serveurs pour l’équilibrage de la charge et la disponibilité des applications fiables, ou sélectionnez le **pool d’un seul ordinateur** si vous n’avez pas besoin de charger de contrepartie ou de haute disponibilité.
  
> [!IMPORTANT]
> Un seul serveur d’Applications de confiance ne peut pas être converti en un pool de serveurs plus tard. Si vous pensez qu'avoir besoin d’un pool à l’avenir, vous pouvez déployer un pool de serveurs multiples contenant un seul ordinateur maintenant et ajouter des serveurs, lorsque cela est nécessaire. 
  
Pour plus d’informations sur les pools d’Applications sécurisées, consultez [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

