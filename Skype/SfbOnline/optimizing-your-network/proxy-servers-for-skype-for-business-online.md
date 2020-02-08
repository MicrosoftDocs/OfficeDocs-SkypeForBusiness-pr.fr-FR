---
title: Serveurs proxy pour Skype Entreprise Online et Teams
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
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Skype entreprise.
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863748"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>Serveurs proxy pour Skype entreprise Online

Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec Skype entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

Lorsqu’il s’agit du trafic de Skype entreprise sur proxy, Microsoft recommande de contournement des proxys. Les proxys ne permettent pas de sécuriser Skype entreprise, car le trafic est déjà crypté.
  
Un serveur proxy peut poser des problèmes. Les problèmes liés aux performances peuvent être introduits dans l’environnement par le biais d’une latence et d’une perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative de ces équipes ou des scénarios Skype entreprise tels que les flux audio et vidéo, où les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n'ont pas d'autres choix que d'utiliser un serveur proxy pour le trafic Skype Entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- Suivi des autres recommandations de nos directives relatives à la mise en réseau :
    
  - [Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online](media-quality-and-network-connectivity-performance.md)
    
  - [Optimisation de votre réseau pour Skype Entreprise Online](optimizing-your-network.md)
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Rubriques connexes

[Optimisation de votre réseau pour Skype Entreprise Online](optimizing-your-network.md)
 