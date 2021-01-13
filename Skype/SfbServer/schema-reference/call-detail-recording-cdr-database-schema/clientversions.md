---
title: Table ClientVersions dans Skype Entreprise Server 2015
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
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813314"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Table ClientVersions dans Skype Entreprise Server 2015
 
La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primaire  <br/> |Numéro unique identifiant le type et la version de ce client.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Nom de la version.  <br/> |
|**ClientType** <br/> |int  <br/> ||Spécifie le type de client utilisé dans la session. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

