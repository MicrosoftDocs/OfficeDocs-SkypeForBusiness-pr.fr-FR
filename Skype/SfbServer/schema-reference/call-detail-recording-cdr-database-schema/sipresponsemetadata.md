---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.
ms.openlocfilehash: 9fb5921b2ff0c371dc8771ce8627bdae23f651dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630348"
---
# <a name="sipresponsemetadata-table"></a>Table SIPResponseMetaData
 
La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.
  
Ce tableau a été introduit dans Skype Entreprise Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primaire  <br/> |Valeur numérique qui représente le code de réponse SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classification générale pour le code de réponse. Les classifications comprennent : <br/>  1 - Réponses d’information <br/>  2 - Réponses réussies <br/>  3 - Réponses de redirection <br/>  4 - Réponses d’échec du client <br/>  5 -- Réponses de défaillance du serveur <br/>  6 - Réponse d’échec global <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :  <br/> L’appel est en cours de transfert  <br/> |
   

