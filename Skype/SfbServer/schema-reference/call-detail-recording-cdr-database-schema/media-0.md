---
title: Vue média
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue Media stocke des informations sur un type de support utilisé dans une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 148f74117ba42849d58e4012e4e963b3ef1b7a3c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898042"
---
# <a name="media-view"></a>Vue média
 
La vue Media stocke des informations sur un type de support utilisé dans une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans le tableau, si plus d’un type de média est utilisé. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue Media ne doit pas être utilisée pour calculer la durée d’une session multimédia. Cet affichage contient les détails de signalisation d’échanges multimédias dans une session. Échanges multimédias est effectué à la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. Le temps d’inviter ne signifie pas nécessairement que le support de démarrage, car media commence uniquement une fois que la session est acceptée. 
  
La vue Media contient toutes les colonnes de [SessionDetails view](sessiondetails-0.md) en plus celles répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Type de média. Consultez la [table MediaList](medialist.md) pour plus d’informations. <br/> |
|**MediaStartTime** <br/> |DateHeure  <br/> |Heure à laquelle une demande de support a été envoyée.  <br/> |
|**MediaEndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
   

