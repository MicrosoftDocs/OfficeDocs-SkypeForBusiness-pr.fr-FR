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
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui contient la liste de types d’appels possibles.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813364"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Table CallType dans Skype Entreprise Server 2015
 
La table CallType est une table statique qui contient la liste de types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primaire  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées : <br/>  0 - Inconnu <br/>  1 - Messagerie instantanée <br/>  2 -- Partage d’application <br/>  3 - Audio <br/>  4 - Audio et vidéo <br/>  5 - Transfert de fichiers <br/> |
   

