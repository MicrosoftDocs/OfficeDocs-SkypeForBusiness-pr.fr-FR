---
title: Affichage UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 22dcd5e127e123e027448ccddaa79007cfdbfe8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420817"
---
# <a name="useragent-view"></a>Affichage UserAgent
 
L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numéro unique qui identifie cet agent utilisateur.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur.  <br/> |
|UAType  <br/> |smallint  <br/> |Type d’agent utilisateur. Pour plus [d’informations, voir le tableau UserAgent](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au standard automatique de conférence (CAA) UACategory.  <br/> |
   

