---
title: Table DeRegisterType dans Skype entreprise Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple « client lancé », « inscription expirée » ou « le client a cessé de répondre ».
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815292"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Table DeRegisterType dans Skype entreprise Server 2015
 
La table DeRegisterType est une table statique qui stocke la liste de types de déregistreurs d’utilisateurs possibles, par exemple « client lancé », « inscription expirée » ou « le client a cessé de répondre ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0--Inconnu <br/>  1--le client a démarré la suppression <br/>  2--inscription expirée <br/>  3-client bloqué <br/>  4--attributs utilisateur modifiés <br/>  5-Bureau d’enregistrement préféré modifié <br/>  6--client hérité en mode de survie <br/> |
   

