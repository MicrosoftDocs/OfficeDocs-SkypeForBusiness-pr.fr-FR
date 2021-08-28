---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: 1e6e70835865f2ca6ef992a879dad58011a5170c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613834"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
  
**Colonnes**

|**Colonne**|**Type (Type)**|**Description**|
|:-----|:-----|:-----|
|serverID  <br/> |int, non null  <br/> |ID de serveur. Correspond à l’ID d’instance du magasin central de gestion.  <br/> |
|serverAddress  <br/> |nvarchar (256), non null  <br/> |Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).  <br/> |
|serverLastPingTime  <br/> |DateHeure  <br/> |Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|serverID  <br/> |Clé primaire.  <br/> |
   

