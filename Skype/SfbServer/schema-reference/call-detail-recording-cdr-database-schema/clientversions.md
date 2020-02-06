---
title: Table ClientVersions dans Skype entreprise Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table qui contient une liste des différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815402"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Table ClientVersions dans Skype entreprise Server 2015
 
La table ClientVersions est une table qui contient une liste des différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Principal  <br/> |Numéro unique identifiant ce type et version de client.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Nom de la version.  <br/> |
|**TypeClient** <br/> |int  <br/> ||Spécifie le type de client utilisé dans la session. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
   

