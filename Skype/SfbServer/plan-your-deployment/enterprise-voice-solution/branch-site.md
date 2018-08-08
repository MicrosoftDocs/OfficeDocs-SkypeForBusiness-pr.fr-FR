---
title: Acheminement SIP dans Skype pour Business Server Branch site
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Découvrez l’acheminement SIP sur les sites de succursale dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: e14d6ba3101c1981b719ea0f030d2e92fbd4ab7b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966270"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Acheminement SIP dans Skype pour Business Server Branch site
 
Découvrez l’acheminement SIP sur les sites de succursale dans Skype pour Business Server Enterprise Voice.
  
Dans certains cas, vous devrez implémenter la jonction SIP distribuée au niveau des sites de succursale sélectionné. Pour déterminer si un SIP trunk est nécessaire pour un site de succursale et pour plus d’informations sur les options de topologie prise en charge pour le déploiement de jonctions SIP dans les sites de succursale, voir la [jonction SIP dans Skype pour Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer une jonction SIP du site succursale, vous devez effectuer une analyse des coûts spécifiques au site. Par exemple, une entreprise qui dispose d’un site central à Redmond, Washington et un site de succursale de New York, doit effectuer une analyse pour déterminer s’il convient d’implémenter une jonction SIP à partir du site de New York à un fournisseur de service local.
  
Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir une terminaison d’arrivée pour le site de succursale sur le site central. Par exemple, le site central Redmond peut héberger les numéros DID pour le site de succursale de New York. Si le coût d’implémentation d’une jonction SIP distribuée est inférieure au coût de ces appels, envisagez d’implémenter une jonction SIP sur le site de succursale de New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez une jonction SIP du site succursale, vous devez également déterminer vos besoins en bande passante et de résistance. Si le lien entre votre site de succursale et le site central est robuste et a suffisamment de bande passante, vous pouvez déployer une jonction SIP ou une passerelle. Il est inutile de déployer un serveur Survivable Branch Appliance sur le site de succursale. Si le lien entre votre site de succursale et le site central n’est pas robuste, déployer un serveur Survivable Branch Appliance ou déployer un serveur Survivable Branch Server avec une passerelle ou une jonction SIP sur le site de succursale. 
  

