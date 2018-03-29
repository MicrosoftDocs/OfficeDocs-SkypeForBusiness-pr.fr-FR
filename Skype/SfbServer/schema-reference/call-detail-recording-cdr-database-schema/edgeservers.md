---
title: Table EdgeServers dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: La table EdgeServers est un tableau de prise en charge. Chaque enregistrement stocke des informations sur un serveur de transport Edge qui est impliqué dans les appels ayant des enregistrements dans la base de données.
ms.openlocfilehash: 581dfcb6bbd3b5088af2bbc27a580d791b9ef8f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Table EdgeServers dans Skype pour Business Server 2015
 
La table EdgeServers est un tableau de prise en charge. Chaque enregistrement stocke des informations sur un serveur de transport Edge qui est impliqué dans les appels ayant des enregistrements dans la base de données.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Principal  <br/> |Numéro unique qui identifie ce serveur de transport Edge.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> | <br/> |Nom du serveur Edge.  <br/> |
   

