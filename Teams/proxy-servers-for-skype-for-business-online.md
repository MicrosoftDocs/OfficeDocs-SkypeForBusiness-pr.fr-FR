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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy Microsoft Teams ou Skype Entreprise.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117722"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Teams ou Skype Entreprise Online

Cet article fournit des conseils sur l’utilisation d’un serveur proxy Teams ou Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne l Teams ou Skype Entreprise trafic sur les serveurs, Microsoft recommande d’ignorer les serveurs proxies. Lesxies ne sécurisationnt pas Teams ou Skype Entreprise,car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels problèmes entraînent une expérience négative dans les scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, pour lequel les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont pas d’autres choix que d’utiliser un proxy Teams ou Skype Entreprise trafic. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- En suivant les autres recommandations de nos directives en matière de mise en réseau : Préparer le réseau de votre organisation [pour l’Teams](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Sujets associés

[Principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)