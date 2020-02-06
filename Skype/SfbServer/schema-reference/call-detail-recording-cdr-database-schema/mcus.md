---
title: Table MCU dans Skype entreprise Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: La table MCU est une table de support. Chaque enregistrement stocke les informations relatives à un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V.
ms.openlocfilehash: 1e5141ee2a103e540d3ac50e99de0036f31262d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815062"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Table MCU dans Skype entreprise Server 2015
 
La table MCU est une table de support. Chaque enregistrement stocke les informations relatives à un service de conférence. Il peut s’agir du service de conférence par messagerie instantanée et du service de conférence téléphonique (qui s’exécutent sous forme de processus sur les serveurs frontaux), du service de conférence Web et du service de conférence A/V. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce serveur de conférence.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Externes <br/> |Le type de serveur de conférence, tel que conf : chat (pour les messages instantanés) ou conf : audio-vidéo. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
   

