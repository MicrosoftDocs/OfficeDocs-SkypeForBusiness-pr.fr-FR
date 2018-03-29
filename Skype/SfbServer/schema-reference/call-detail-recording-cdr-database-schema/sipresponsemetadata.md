---
title: Table de SIPResponseMetaData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse aux événements affectant les équipements SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP fait une demande, mais le serveur refuse d’honorer la demande.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>Table de SIPResponseMetaData
 
La SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse aux événements affectant les équipements SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP fait une demande, mais le serveur refuse d’honorer la demande.
  
Cette table a été introduite dans Skype pour Business Server 2015.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principal  <br/> |Valeur numérique qui représente le code de réponse SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classification générale pour le code de réponse. Les classifications sont les suivantes : <br/>  1 - réponses d’information <br/>  2 - réponses réussis <br/>  3 - réponses de redirection <br/>  4 - réponses Échec de la client <br/>  5--Réponses d’échec serveur <br/>  6 - réponse d’échec global <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :  <br/> Appel est transmis  <br/> |
   

