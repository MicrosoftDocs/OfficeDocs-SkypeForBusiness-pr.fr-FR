---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924807"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contient les serveurs de conversation actifs dans le pool de serveurs de conversation permanente.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|serverID  <br/> |int, non null  <br/> |ID du serveur. Correspond à l’ID de l’instance du magasin Central de gestion.  <br/> |
|serverAddress  <br/> |nvarchar (256), non null  <br/> |Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |DateHeure  <br/> |La dernière heure à laquelle le serveur de canal mis à jour cette ligne pour faire la preuve de son exécution.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|serverID  <br/> |Clé primaire.  <br/> |
   

