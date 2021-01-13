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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823264"
---
# <a name="phones-table"></a>Table Phones
 
La table Phones est une table de prise en charge. Chaque enregistrement de la table stocke des informations sur un numéro de téléphone impliqué dans les appels VoIP qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce téléphone.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Numéro de téléphone.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Horodaté (pour une utilisation interne uniquement).  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
   

