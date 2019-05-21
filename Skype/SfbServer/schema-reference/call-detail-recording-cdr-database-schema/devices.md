---
title: Tableau des appareils dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296377"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tableau des appareils dans Skype entreprise Server 2015
 
Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette version matérielle.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externes  <br/> |Fabricant de cet appareil. Pour plus d’informations, reportez-vous [à la table constructeurs dans Skype entreprise Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externes  <br/> |Version matérielle de cet appareil. Pour plus d’informations, reportez-vous [à la table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

