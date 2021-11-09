---
title: Table Devices dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: bffa7bc59e2c1b52b3586d89f5f9c3828a569a26
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857241"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Table Devices dans Skype Entreprise Server 2015
 
La table Devices est une table de prise en charge. Chaque enregistrement stocke des informations sur un appareil (téléphone de bureau).
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant cette version du matériel.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Étranger  <br/> |Fabricant de cet appareil. Pour plus d’informations, voir le tableau [Manufacturers Skype Entreprise Server 2015.](manufacturers.md) <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Étranger  <br/> |Version du matériel de cet appareil. Pour plus [d’informations, voir le tableau HardwareVersions Skype Entreprise Server 2015.](hardwareversions.md) <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Adresse MAC  <br/> |
   

