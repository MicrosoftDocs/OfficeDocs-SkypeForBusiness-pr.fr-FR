---
title: Table CallType dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 7f00e924041c5b26f7045cf8f97ae82daa141611
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845087"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Table CallType dans Skype Entreprise Server 2015
 
La table CallType est une table statique qui contient la liste de types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primaire  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Messagerie instantanée <br/>  2 -- Partage d’application <br/>  3 - Audio <br/>  4 - Audio et vidéo <br/>  5 - Transfert de fichiers <br/> |
   

