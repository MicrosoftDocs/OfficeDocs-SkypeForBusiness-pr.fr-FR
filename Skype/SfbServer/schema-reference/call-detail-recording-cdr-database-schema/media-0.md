---
title: Affichage multimédia
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 2ed8d66bf55594e3524a43b35df3bfa6d859055a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828557"
---
# <a name="media-view"></a>Affichage multimédia
 
La vue Media stocke des informations sur un type de média utilisé au cours d’une session d’égal à égal. Une session est représentée par plusieurs enregistrements dans la table, si plusieurs types de médias sont utilisés. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue Media ne doit pas être utilisée pour calculer la durée du média lors d’une session. Cette vue contient les détails de signalisation de l’échange multimédia lors d’une session. L’échange multimédia est effectué par la requête INVITE et StartTime indique l’heure à laquelle la requête INVITE a été envoyée. L’heure d’invitation ne signifie pas nécessairement l’heure de début du média, car le média démarre seulement une fois la session acceptée. 
  
L’affichage Multimédia contient toutes les colonnes de l’affichage [SessionDetails](sessiondetails-0.md) en plus de ceux répertoriés ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Type de média. Pour plus [d’informations, voir le tableau MediaList.](medialist.md) <br/> |
|**MediaStartTime** <br/> |DateHeure  <br/> |Heure d’envoi d’une demande multimédia.  <br/> |
|**MediaEndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
   

