---
title: Jonction SIP de site de succursale dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Découvrez le trunking SIP sur les sites des succursales dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 92616062c12fce51e3adb816d5ebc299a5dbf3fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a>Jonction SIP de site de succursale dans Skype Entreprise Server 2015
 
Découvrez le trunking SIP sur les sites des succursales dans Skype pour Business Server Voix Entreprise.
  
Dans certains cas, vous devrez implémenter distribué trunking SIP sur les sites de la branche sélectionnée. Pour déterminer si un SIP trunk est nécessaire pour un site de la succursale et pour plus d’informations sur les options de topologie prise en charge pour le déploiement de troncs SIP dans les sites des succursales, consultez [SIP trunking dans Skype pour Business Server 2015](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer un tronc SIP de site de succursale, vous devez effectuer une analyse des coûts spécifiques au site. Par exemple, une entreprise qui dispose d’un site central à Redmond, Washington et un site de la succursale de New York, doit effectuer une analyse pour déterminer s’il faut implémenter un SIP trunk à partir du site de New York à un fournisseur de services local.
  
Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir arrêt DID pour le site de la succursale sur le site central. Par exemple, le site central de Redmond peut héberger des numéros DID pour le site de la succursale de New York. Si le coût de l’implémentation d’un SIP trunk distribué est inférieur au coût de ces appels, envisagez d’implémenter un SIP trunk au site de la succursale de New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez un tronc SIP de site de succursale, vous devez également déterminer vos besoins en matière de résilience et de la bande passante. Si le lien entre le site de la succursale et le site central est souple et une bande passante suffisante, vous pouvez déployer une jonction SIP ou une passerelle. Vous n’avez pas besoin de déployer un Survivable Branch Appliance sur le site de la succursale. Si le lien entre le site de la succursale et le site central n’est pas souple, déployer un Survivable Branch Appliance, ou déployer un serveur Survivable Branch Server avec une passerelle ou un SIP trunk sur le site de la succursale. 
  

