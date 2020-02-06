---
title: Affichage UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: L’affichage UserAgent stocke les informations sur les agents utilisateur impliqués dans les sessions qui contiennent des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805082"
---
# <a name="useragent-view"></a>Affichage UserAgent
 
L’affichage UserAgent stocke les informations sur les agents utilisateur impliqués dans les sessions qui contiennent des enregistrements dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Numéro unique identifiant cet agent utilisateur.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur.  <br/> |
|UAType  <br/> |type  <br/> |Type d’agent utilisateur. Pour plus d’informations, voir la [table UserAgent](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Catégorie à laquelle l’agent utilisateur appartient. Par exemple, l’agent utilisateur Conferencing_Attendant_1.0 appartient au CAA UACategory.  <br/> |
   

