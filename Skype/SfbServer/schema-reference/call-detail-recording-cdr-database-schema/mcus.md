---
title: Table Mcus dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence de messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: 1394a2f899df47b15a66989aeaed5872f6913912
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765092"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table Mcus dans Skype Entreprise Server 2015
 
La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence de messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inynt  <br/> | Étranger <br/> |Type de serveur de conférence, tel que conf:chat (pour les IM) ou conf:audio-video. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
   

