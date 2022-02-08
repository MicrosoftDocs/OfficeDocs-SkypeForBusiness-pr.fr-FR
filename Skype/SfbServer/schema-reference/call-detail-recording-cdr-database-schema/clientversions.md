---
title: Table ClientVersions dans Skype Entreprise Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.
ms.openlocfilehash: dd9afc6addef78bf255e6237f1b29f5cac4ee071
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386323"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a>Table ClientVersions dans Skype Entreprise Server 2015
 
La table ClientVersions est une table de prise en charge qui stocke la liste des divers types et versions de clients ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la table représente une version de client.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**VersionId** <br/> |**int** <br/> |Primaire  <br/> |Numéro unique identifiant le type et la version de ce client.  <br/> |
|**Version** <br/> |**nvarchar(256)** <br/> ||Nom de la version.  <br/> |
|**ClientType** <br/> |int  <br/> ||Spécifie le type de client utilisé dans la session. Pour plus [d’informations, voir la table UserAgentDef](useragentdef.md) . <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

