---
title: Branch site SIP trunking in Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: En savoir plus sur la trunking SIP sur les sites de succursale Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 24c9dd53e8c8ce7a00b38ee50b617e9394b7e88c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387842"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Branch site SIP trunking in Skype Entreprise Server
 
En savoir plus sur la trunking SIP sur les sites de succursale Skype Entreprise Server Voix Entreprise.
  
Dans certains cas, vous devrez peut-être implémenter une trunking SIP distribuée sur des sites de succursale sélectionnés. Pour déterminer si une trunk SIP est nécessaire pour un site de succursale et pour plus d’informations sur les options de topologie prise en charge pour le déploiement de trunks SIP dans des sites de succursale, voir [siP trunking in Skype Entreprise Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer une trunk SIP de site de succursale, vous devez effectuer une analyse des coûts spécifique au site. Par exemple, une entreprise qui possède un site central à Redmond,Washington et un site de succursale à New York, doit réaliser une analyse pour déterminer s’il faut implémenter une trunk SIP du site New York vers un fournisseur de services local.
  
Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir un arrêt DID pour le site de succursale sur le site central. Par exemple, le site central de Redmond peut héberger des numéros DID pour le site de succursale de New York. Si le coût de l’implémentation d’une trunk SIP distribuée est inférieur au coût de ces appels, envisagez d’implémenter une trunk SIP sur le site de succursale de New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez une connexion SIP de site de succursale, vous devez également déterminer vos besoins en résilience et en bande passante. Si la liaison entre votre site de succursale et votre site central est résiliente et dispose d’une bande passante suffisante, vous pouvez déployer une connexion SIP ou une passerelle. Vous n’avez pas besoin de déployer un Survivable Branch Appliance sur le site de succursale. Si la liaison entre votre site de succursale et votre site central n’est pas résiliente, déployez un Survivable Branch Appliance ou déployez un serveur Survivable Branch Server avec une passerelle ou une connexion SIP sur le site de succursale. 
  

