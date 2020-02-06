---
title: Vue multimédia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815052"
---
# <a name="media-view"></a>Vue multimédia
 
Le mode multimédia stocke les informations relatives à un type de média utilisé dans une session d’égal à égal. Une session serait représentée par plusieurs enregistrements dans la table, si plusieurs types de média sont utilisés. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Le mode multimédia ne doit pas être utilisé pour calculer la durée du média pour une session. Cet affichage contient les détails de signalisation d’échange de médias dans une session. L’échange de média est effectué par la demande d’invitation, et la durée de StartTime indique l’heure d’envoi de l’invitation. La durée d’invitation ne correspond pas nécessairement à l’heure de début du média, car le contenu multimédia ne démarre qu’après acceptation de la session. 
  
La vue multimédia contient toutes les colonnes de la [vue SessionDetails](sessiondetails-0.md) , en plus de celles répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**Media** <br/> |nvarchar(256)  <br/> |Type de média. Pour plus d’informations, reportez-vous à la [table de médiane](medialist.md) . <br/> |
|**MediaStartTime** <br/> |DateHeure  <br/> |Temps d’envoi d’une demande de média.  <br/> |
|**MediaEndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
   

