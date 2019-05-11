---
title: Table Mcus dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Le tableau de MCU est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V.
ms.openlocfilehash: 6b5df793008fcf7586d62cab77a1b362848374ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930671"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table Mcus dans Skype pour Business Server 2015
 
Le tableau de MCU est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir le service de conférence par messagerie instantanée et le service de téléconférence (ce qui s’exécutent en tant que processus sur les serveurs frontaux) et que le service de conférence Web et A / service de conférence V. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Étrangère <br/> |Type de serveur de conférence, tel que conf:chat (pour les messages instantanés) ou conf:audio-vidéo. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
   

