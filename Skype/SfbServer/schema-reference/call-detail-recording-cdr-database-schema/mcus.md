---
title: Table de MCU dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table MCU est une table de prise en charge. Chaque enregistrement contient des informations sur un service de conférence. Il peut s’agir du service de conférence de la messagerie instantanée et le service de conférences téléphoniques (qui s’exécutent en tant que processus sur les serveurs frontaux), le service de conférence Web et A / V Conferencing service.
ms.openlocfilehash: 2a85d46e733d230dc7c8096c8804146b19766bcf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table de MCU dans Skype pour Business Server 2015
 
La table MCU est une table de prise en charge. Chaque enregistrement contient des informations sur un service de conférence. Il peut s’agir du service de conférence de la messagerie instantanée et le service de conférences téléphoniques (qui s’exécutent en tant que processus sur les serveurs frontaux), le service de conférence Web et A / V Conferencing service. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principal  <br/> |Numéro unique qui identifie ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Étrangère <br/> |Type de serveur de conférence, par exemple conf:chat (pour IMs) ou conf:audio-vidéo. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

