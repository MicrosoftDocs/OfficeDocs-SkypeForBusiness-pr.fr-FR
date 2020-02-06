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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contient les serveurs de chat actifs dans le pool de serveurs de chat permanent.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812272"
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
   

