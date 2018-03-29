---
title: Table de passerelles dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La table de passerelles est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle qui est impliquée dans les appels de réseau (RTPC) public commuté qui ont des enregistrements dans la base de données.
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Table de passerelles dans Skype pour Business Server 2015
 
La table de passerelles est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle qui est impliquée dans les appels de réseau (RTPC) public commuté qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette passerelle.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> | <br/> |Nom de la passerelle.  <br/> |
   

