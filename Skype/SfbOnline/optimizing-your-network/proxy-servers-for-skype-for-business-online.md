---
title: Serveurs proxy pour Teams ou Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Skype Entreprise.
ms.openlocfilehash: c6c094bad366cf6a7febb092d471dd0723ce219b90664963a5e58a2ce64d70ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323516"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Serveurs proxy pour Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne le trafic Skype Entreprise, Microsoft recommande d'éviter d'utiliser un serveur proxy. En raison de la sécurité du trafic, Skype Entreprise pas sécurisés, car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels problèmes entraînent une expérience négative dans les scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, pour lequel les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- En suivant les autres recommandations de nos directives en matière de mise en réseau :
    
  - [Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md)
    
  - [Optimisation de votre réseau pour Skype Entreprise Online](optimizing-your-network.md)
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Voir aussi

[Optimisation de votre réseau pour Skype Entreprise Online](optimizing-your-network.md)
 
