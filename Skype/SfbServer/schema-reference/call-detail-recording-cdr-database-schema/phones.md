---
title: Table Phones
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 37adaaa1885d91c84ee657c422b19debad294c01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584858"
---
# <a name="phones-table"></a>Table Phones
 
La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce téléphone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Téléphone numéro.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Horodaté (pour une utilisation interne uniquement).  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

