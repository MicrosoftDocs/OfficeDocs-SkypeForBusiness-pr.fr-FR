---
title: Affichage UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: f0e04812928f38d0e9362b08ce160da7e6984df5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580368"
---
# <a name="useragent-view"></a>Affichage UserAgent
 
L’affichage UserAgent stocke les informations relatives aux agents utilisateur qui ont été impliqués dans des sessions ayant des enregistrements dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numéro unique qui identifie cet agent utilisateur.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur.  <br/> |
|UAType  <br/> |smallint  <br/> |Type d’agent utilisateur. Pour plus [d’informations, voir le tableau UserAgent.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Catégorie à laquelle appartient l’agent utilisateur. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au standard automatique de conférence (CAA) UACategory.  <br/> |
   

