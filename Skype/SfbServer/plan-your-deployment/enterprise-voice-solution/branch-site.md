---
title: Trunking SIP site dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: En savoir plus sur le trunking SIP sur les sites de succursales dans Skype entreprise Server Voice.
ms.openlocfilehash: 14af9a096b368f310b0d4fbce425bf6d1c08696a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277110"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Trunking SIP site dans Skype entreprise Server
 
En savoir plus sur le trunking SIP sur les sites de succursales dans Skype entreprise Server Voice.
  
Dans certains cas, il est possible que vous deviez implémenter une agrégation SIP distribuée sur des sites de succursales sélectionnés. Pour déterminer si un Trunk SIP est requis pour un site de succursale et pour plus d’informations sur les options de topologie prises en charge pour le déploiement de Trunks SIP dans les sites de succursales, voir l’interconnexion [SIP dans Skype entreprise Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer un Trunk SIP de site de succursale, vous devez effectuer une analyse de coûts spécifique au site. Par exemple, une entreprise disposant d’un site central dans Redmond, Washington et sur une succursale à New York doit effectuer une analyse pour déterminer s’il est nécessaire de mettre en œuvre un Trunk SIP à partir du site de New York vers un fournisseur de services local.
  
Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir terminé le site de succursale sur le site central. Par exemple, le site central de Redmond peut héberger des numéros ayant été importés pour le site de succursale de New York. Si le coût de l’implémentation d’un Trunk SIP distribué est inférieur au coût de ces appels, envisagez d’implémenter une ligne SIP sur le site de la succursale de New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez une ligne SIP site de succursale, vous devez également déterminer votre tolérance de panne et vos besoins en bande passante. Si le lien entre votre site de succursale et votre site central est résilient et dispose d’une bande passante suffisante, vous pouvez déployer une passerelle SIP. Vous n’avez pas besoin de déployer une unité de branchement survivant sur le site de la succursale. Si le lien entre votre site de succursale et votre site central n’est pas résilient, déployez une application de succursale survivant ou déployez un serveur de succursales survivant avec une passerelle ou une ligne SIP sur le site de la succursale. 
  

