---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: La SIPResponseMetaDataTable contient une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générées en réponse aux événements affectant des périphériques SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais le serveur refuse de respecter cette demande.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930284"
---
# <a name="sipresponsemetadata-table"></a>Table SIPResponseMetaData
 
La SIPResponseMetaDataTable contient une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générées en réponse aux événements affectant des périphériques SIP et SIP des sessions de communication ; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais le serveur refuse de respecter cette demande.
  
Ce tableau a été introduit dans Skype pour Business Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principal  <br/> |Valeur numérique qui représente le code de réponse SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classification générale pour le code de réponse. Classifications sont les suivantes : <br/>  1 - réponses informatives <br/>  2 - réponses réussite <br/>  3 - réponses de redirection <br/>  4 - réponses d’échec de client <br/>  5--Réponses d’échec de serveur <br/>  6 - réponse d’échec global <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :  <br/> Appel est transféré.  <br/> |
   

