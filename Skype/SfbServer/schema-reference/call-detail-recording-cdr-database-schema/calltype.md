---
title: Table CallType dans Skype Entreprise Server 2015
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui contient la liste de types d’appels possibles.
ms.openlocfilehash: 7c84e245cac2ceb25a5012f9caf4a2a31d4cb67b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620910"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Table CallType dans Skype Entreprise Server 2015
 
La table CallType est une table statique qui contient la liste de types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primaire  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Messagerie instantanée <br/>  2 -- Partage d’application <br/>  3 - Audio <br/>  4 - Audio et vidéo <br/>  5 - Transfert de fichiers <br/> |
   

