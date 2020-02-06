---
title: Table !Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table Telephones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui contiennent des enregistrements dans la base de données.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815002"
---
# <a name="phones-table"></a>Table !Phones
 
La table Telephones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui contiennent des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce téléphone.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Numéro de téléphone.  <br/> |
|**NextUpdateTS** <br/> |Valeur  <br/> ||Horodatage (pour une utilisation interne uniquement).  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
   

