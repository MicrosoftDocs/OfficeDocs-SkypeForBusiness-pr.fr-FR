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
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303657"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|serverID  <br/> |int, non null  <br/> |ID de serveur. Correspond à l’ID d’instance du magasin central de gestion.  <br/> |
|serverAddress  <br/> |nvarchar (256), non null  <br/> |Adresse de serveur utilisant l’adresse WCF (Windows Communication Foundation).  <br/> |
|serverLastPingTime  <br/> |DateHeure  <br/> |Dernière fois où le serveur de canal a mis à jour cette ligne pour faire la preuve de son exécution.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|serverID  <br/> |Clé primaire.  <br/> |
   

