---
title: Table Gateways dans Skype Entreprise Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: La table Gateways est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle impliquée dans des appels de réseau téléphonique commuté (PSTN) qui ont des enregistrements dans la base de données.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821584"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Table Gateways dans Skype Entreprise Server 2015
 
La table Gateways est une table de prise en charge. Chaque enregistrement stocke des informations sur une passerelle impliquée dans des appels de réseau téléphonique commuté (PSTN) qui ont des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cette passerelle.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> | <br/> |Nom de la passerelle.  <br/> |
   

