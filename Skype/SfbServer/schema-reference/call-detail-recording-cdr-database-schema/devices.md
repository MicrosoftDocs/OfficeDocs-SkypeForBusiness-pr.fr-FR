---
title: Table Devices dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
ms.openlocfilehash: fc33e7fbffa3e35301e7d6b17a491aa84190c5ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620890"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Table Devices dans Skype Entreprise Server 2015
 
La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cette version du matériel.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Étranger  <br/> |Fabricant de cet appareil. Pour plus d’informations, voir le tableau [Manufacturers Skype Entreprise Server 2015.](manufacturers.md) <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Étranger  <br/> |Version du matériel de cet appareil. Pour plus [d’informations, voir le tableau HardwareVersions Skype Entreprise Server 2015.](hardwareversions.md) <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

