---
title: Ajouter un nom de domaine complet du pool d’applications approuvées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Pour définir le nom de domaine complet (FQDN) du pool d’applications approuvées, vous précisez les éléments suivants :'
ms.openlocfilehash: 94cf0f611d754dc614111add734bf231c92c5a81
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217005"
---
# <a name="add-trusted-application-pool-fqdn"></a>Ajouter un nom de domaine complet du pool d’applications approuvées
 
Pour définir le nom de domaine complet (FQDN) du pool d’applications approuvées, vous précisez les éléments suivants :
  
Le nom de domaine complet du serveur ou du pool de serveurs qui hébergent les applications approuvées.
  
Sélectionnez **Pool de plusieurs ordinateurs** si vous déployez un pool de serveurs pour les applications approuvées d’équilibrage de charge et de haute disponibilité, ou bien sélectionnez **Pool d’un seul ordinateur** si vous n’avez pas besoin d’équilibrage de charge ou de haute disponibilité.
  
> [!IMPORTANT]
> Un seul serveur d’applications approuvées ne peut pas se convertir en pool de serveurs par la suite. Si vous pensez avoir besoin d’un pool dans le futur, vous pouvez déployer dès maintenant un pool de plusieurs serveurs ne contenant qu’un seul ordinateur, puis ajouter des serveurs le cas échéant. 
  
Pour plus d’informations sur les pools d’applications approuvées, voir [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

