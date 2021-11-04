---
title: Table DeRegisterType dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des types d’utilisateurs dé-inscrits possibles, tels que « initié par le client » ou « l’inscription a expiré » ou « le client a cessé de répondre ».
ms.openlocfilehash: f369416a15f0b1c024dd70fbe97042193940f669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743990"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Table DeRegisterType dans Skype Entreprise Server 2015
 
La table DeRegisterType est une table statique qui stocke la liste des types d’utilisateurs dé-inscrits possibles, tels que « initié par le client » ou « l’inscription a expiré » ou « le client a cessé de répondre ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primaire  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 -- Inconnu <br/>  1 -- Désinscription à l’initiative du client <br/>  2 -- Expiration de l’inscription <br/>  3 - Le client s’est crashé <br/>  4 -- Modification des attributs de l’utilisateur <br/>  5 - Bureau d’enregistrement préféré modifié <br/>  6 -- Client hérité en mode survie <br/> |
   

