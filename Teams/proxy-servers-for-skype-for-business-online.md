---
title: Serveurs proxy pour Teams ou Skype Entreprise Online
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Microsoft Teams ou Skype Entreprise.
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045433"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Teams ou Skype Entreprise Online

Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Teams ou Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

Lorsqu’il s’agit de Teams ou de Skype Entreprise le trafic via des proxys, Microsoft recommande de contourner les proxys. Les proxys ne rendent pas Teams ou Skype Entreprise plus sécurisés, car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Ces problèmes entraînent une expérience négative dans des scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, où les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont pas la possibilité de contourner un proxy pour Teams ou Skype Entreprise trafic. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- Suivez les autres recommandations de nos recommandations en matière de mise en réseau : [Préparer le réseau de votre organisation pour Teams](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Voir aussi

[Principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)