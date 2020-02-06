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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815282"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tableau des appareils dans Skype entreprise Server 2015
 
Le tableau appareils est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cette version matérielle.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externes  <br/> |Fabricant de cet appareil. Pour plus d’informations, reportez-vous [à la table constructeurs dans Skype entreprise Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externes  <br/> |Version matérielle de cet appareil. Pour plus d’informations, reportez-vous [à la table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

