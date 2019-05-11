---
title: Vue UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La vue UserAgent stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 942093ece5706115cc4e90171c09df8a8a169b09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907023"
---
# <a name="useragent-view"></a>Vue UserAgent
 
La vue UserAgent stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numéro unique identifiant cet agent utilisateur.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur.  <br/> |
|UAType  <br/> |smallint  <br/> |Type d’agent utilisateur. Voir la [table UserAgent](useragent.md) pour plus d’informations. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient à la CAA UACategory.  <br/> |
   

