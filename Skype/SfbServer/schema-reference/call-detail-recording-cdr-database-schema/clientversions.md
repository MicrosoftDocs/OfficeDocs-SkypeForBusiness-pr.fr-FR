---
title: Table ClientVersions dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table de prise en charge qui stocke une liste des différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: 86711c89baf374576ee53c64a67688cde10103cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901442"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Table ClientVersions dans Skype pour Business Server 2015
 
La table ClientVersions est une table de prise en charge qui stocke une liste des différents types de clients et les versions qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principal  <br/> |Numéro unique identifiant ce type de client et de la version.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Nom de la version.  <br/> |
|**TypeClient** <br/> |int  <br/> ||Spécifie le type du client utilisé dans la session. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

