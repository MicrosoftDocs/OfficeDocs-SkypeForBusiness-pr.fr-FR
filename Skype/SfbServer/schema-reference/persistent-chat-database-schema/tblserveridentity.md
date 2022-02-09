---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398608"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|serverID  <br/> |int, non null  <br/> |ID de serveur. Correspond à l’ID d’instance du magasin central de gestion.  <br/> |
|serverAddress  <br/> |nvarchar (256), non null  <br/> |Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).  <br/> |
|serverLastPingTime  <br/> |DateHeure  <br/> |Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|serverID  <br/> |Clé primaire.  <br/> |
   

