---
title: CallType table dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: La table CallType est une table statique qui contient la liste des types d’appels possibles.
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296559"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>CallType table dans Skype entreprise Server 2015
 
La table CallType est une table statique qui contient la liste des types d’appels possibles.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Principal  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Valeurs autorisées: <br/>  0--Inconnu <br/>  1-messagerie instantanée <br/>  2-partage d’application <br/>  3-audio <br/>  4-audio et vidéo <br/>  5-transfert de fichiers <br/> |
   

