---
title: Table Mcus dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Le tableau de MCU est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893011"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table Mcus dans Skype pour Business Server 2015
 
Le tableau de MCU est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Étrangère <br/> |Type de serveur de conférence, tel que conf:chat (pour les messages instantanés) ou conf:audio-vidéo. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

