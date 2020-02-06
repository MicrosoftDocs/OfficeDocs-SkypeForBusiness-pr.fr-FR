---
title: Table Media
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Chaque enregistrement représente un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés.
ms.openlocfilehash: b96f1e9fccf2ac3416e505eb19a54a5e227bb01f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815042"
---
# <a name="media-table"></a>Table Media
 
Chaque enregistrement représente un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés.
  
> [!NOTE]
> La table multimédia ne doit pas être utilisée pour calculer la durée du média pour une session. Ce tableau contient les détails de signalisation d’échange de médias dans une session. L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après que la session de la session a été acceptée. Le heure_fin correspond généralement à l’heure de fin de la session. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**MediaId** <br/> |tinyint  <br/> |Etranger principal  <br/> |Numéro unique identifiant ce type de média. Pour plus d’informations, reportez-vous à la [table de médiane](medialist.md) . <br/> |
|**StartTime** <br/> |DateHeure  <br/> |Principal  <br/> |Il s’agit du temps d’envoi d’une demande de média et non de l’heure de début réelle du média. **StartTime** inclut le temps de configuration de la session. <br/> |
|**EndTime** <br/> |DateHeure  <br/> ||Il s’agit de l’heure de fin de la session.  <br/> |
   

