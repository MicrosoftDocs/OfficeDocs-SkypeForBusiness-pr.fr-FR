---
title: Vue média
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue média stocke des informations sur un type de support utilisé dans une session peer-to-peer. Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a>Vue média
 
La vue média stocke des informations sur un type de support utilisé dans une session peer-to-peer. Une session est représentée par plusieurs enregistrements de la table, si plus d’un type de média est utilisé. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue média ne doit pas servir pour calculer la durée d’une session de média. Cette vue contient les détails de signalisation de l’échange de médias dans une session. Échange de médias est effectué par la demande d’invitation et StartTime indique l’heure à laquelle l’invitation a été envoyée. L’heure de l’invitation ne signifie pas nécessairement que le support de démarrage, car le média ne démarre qu’après que la session est acceptée. 
  
La vue média contient toutes les colonnes dans la [vue de le SessionDetails](sessiondetails-0.md) en outre ceux répertoriés ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Type de média. Consultez le [tableau de MediaList](medialist.md) pour plus d’informations. <br/> |
|**MediaStartTime** <br/> |DateHeure  <br/> |Heure à laquelle une demande de support a été envoyée.  <br/> |
|**MediaEndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
   

