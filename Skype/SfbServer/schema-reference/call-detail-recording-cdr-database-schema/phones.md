---
title: Table !Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Le tableau de téléphones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894641"
---
# <a name="phones-table"></a>Table !Phones
 
Le tableau de téléphones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP disposant d’enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce téléphone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Numéro de téléphone.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Horodatage (pour une utilisation interne uniquement).  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

