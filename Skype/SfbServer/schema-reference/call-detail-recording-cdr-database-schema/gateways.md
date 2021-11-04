---
title: Table Gateways dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La table Gateways est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle impliquée dans des appels de réseau téléphonique commuté (PSTN) qui ont des enregistrements dans la base de données.
ms.openlocfilehash: 35b552239d272f47d1f21c0940620dda4e6f075d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777754"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Table Gateways dans Skype Entreprise Server 2015
 
La table Gateways est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle impliquée dans des appels de réseau téléphonique commuté (PSTN) qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cette passerelle.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> | <br/> |Nom de la passerelle.  <br/> |
   

