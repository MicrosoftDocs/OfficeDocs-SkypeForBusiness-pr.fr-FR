---
title: Table Media
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Chaque enregistrement représente un type de média utilisé dans une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé.
ms.openlocfilehash: 76441c350241415aacac150e1e5dec2638302075
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930643"
---
# <a name="media-table"></a>Table Media
 
Chaque enregistrement représente un type de média utilisé dans une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé.
  
> [!NOTE]
> La table Media ne doit pas être utilisée pour calculer la durée d’une session multimédia. Cette table contient les détails de signalisation d’échanges multimédias dans une session. Échanges multimédias est effectué à la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. Le temps d’inviter ne signifie pas nécessairement que le support de démarrage, car media commence uniquement une fois que le sessionee accepte la session. L’heure de fin signifie généralement que l’heure de fin de cette session. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**MediaId** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant ce type de média. Consultez la [table MediaList](medialist.md) pour plus d’informations. <br/> |
|**StartTime** <br/> |DateHeure  <br/> |Principal  <br/> |Il s’agit de l’heure à laquelle une demande de support a été envoyée, heure de début non au support réel. **StartTime** inclut la durée de configuration de session. <br/> |
|**EndTime** <br/> |DateHeure  <br/> ||Il s’agit de l’heure de fin de la session.  <br/> |
   

