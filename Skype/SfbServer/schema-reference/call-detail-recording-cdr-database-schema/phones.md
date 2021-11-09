---
title: Table Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 249b2a08e0751b6e8746f2da27a13e1151c375f7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836102"
---
# <a name="phones-table"></a>Table Phones
 
La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce téléphone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Téléphone numéro.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Horodaté (pour une utilisation interne uniquement).  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

