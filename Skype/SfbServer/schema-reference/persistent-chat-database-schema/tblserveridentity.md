---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295187"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.
  
**Celles**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|serverID  <br/> |ent, non null  <br/> |ID du serveur. Correspond à l’ID de l’instance du magasin central de gestion.  <br/> |
|serverAddress  <br/> |nvarchar (256), pas null  <br/> |Adresse du serveur à l’aide de l’adresse Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |DateHeure  <br/> |Dernière mise à jour de cette ligne par le serveur de canal pour indiquer qu’il est en cours d’exécution.  <br/> |
   
**Clé**

|**Colonne**|**Description**|
|:-----|:-----|
|serverID  <br/> |Clé primaire.  <br/> |
   

