---
title: Table AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: fcb0323b1e6775b20a8ca4d269bcc8eecdc055b73d5a93a490e97f8a1af44b11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305346"
---
# <a name="appliedbandwidthsource-table"></a>Table AppliedBandwidthSource
 
La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de cette source.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Uniques  <br/> |Il s’agit de la source de la capacité de bande passante imposée. Il décrit l’emplacement d’où vient la limite de bande passante (par exemple, « Serveur de stratégie », « SERVEUR TURN » ou « Modalité »).  <br/> |
   

