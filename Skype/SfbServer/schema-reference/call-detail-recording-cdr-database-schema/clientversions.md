---
title: Table ClientVersions dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est un tableau de prise en charge qui stocke une liste des différents types de client et de versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Table ClientVersions dans Skype pour Business Server 2015
 
La table ClientVersions est un tableau de prise en charge qui stocke une liste des différents types de client et de versions qui ont participé aux sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version du client.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Valeur de VersionId** <br/> |**int** <br/> |Principal  <br/> |Numéro unique identifiant le type de client et de la version.  <br/> |
|**Version** <br/> |**nvarchar (256)** <br/> ||Nom de la version.  <br/> |
|**TypeClient** <br/> |int  <br/> ||Spécifie le type de client utilisé dans la session. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus d’informations. <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

