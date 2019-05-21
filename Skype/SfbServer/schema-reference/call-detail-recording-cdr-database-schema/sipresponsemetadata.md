---
title: Table SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295789"
---
# <a name="sipresponsemetadata-table"></a>Table SIPResponseMetaData
 
Le SIPResponseMetaDataTable contient une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes. Ces codes sont générés en réponse à des événements affectant des périphériques SIP et des sessions de communication SIP; par exemple, le code de réponse 403 est généré lorsqu’un périphérique SIP envoie une demande, mais que le serveur décline la demande.
  
Ce tableau a été présenté dans Skype entreprise Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principal  <br/> |Valeur numérique qui représente le code de réponse SIP.  <br/> |
|**Cours** <br/> |int  <br/> || Classification générale du code de réponse. Les classifications sont les suivantes: <br/>  1-réponses d’information <br/>  2-réponses réussies <br/>  3-réponses de redirection <br/>  4-réponses de défaillance client <br/>  5 réponses aux échecs sur le serveur <br/>  6-réponse d’échec globale <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||Description du code de réponse SIP. Par exemple, le code de réponse 181 contient la description suivante:  <br/> Appel en cours de transfert  <br/> |
   

