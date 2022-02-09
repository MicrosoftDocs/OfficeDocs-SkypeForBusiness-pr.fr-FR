---
title: Table Mcus dans Skype Entreprise Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence de messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: 3cd0e096a09f1b83d50d4b7cad8428318d7fdb51
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416377"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table Mcus dans Skype Entreprise Server 2015
 
La table Mcus est une table de prise en charge. Chaque enregistrement stocke des informations sur un service de conférence. Il peut s’agir du service de conférence de messagerie instantanée et du service de conférence téléphonique (qui s’exécutent en tant que processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inynt  <br/> | Étranger <br/> |Type de serveur de conférence, tel que conf:chat (pour les IM) ou conf:audio-video. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
   

