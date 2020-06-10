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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Microsoft teams ou Skype entreprise.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665956"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Skype Entreprise Online et Teams

Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec teams ou Skype entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

Lorsque le trafic est lié aux équipes ou à Skype entreprise via des proxys, Microsoft recommande de contournement des proxys. Les proxys ne permettent pas de sécuriser les équipes ou Skype entreprise, car le trafic est déjà crypté.
  
Un serveur proxy peut poser des problèmes. Les problèmes liés aux performances peuvent être introduits dans l’environnement par le biais d’une latence et d’une perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative de ces équipes ou des scénarios Skype entreprise tels que les flux audio et vidéo, où les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont aucune option pour contourner un proxy pour le trafic d’équipes ou Skype entreprise. Si tel est le cas, vous devez garder à l’esprit les problèmes mentionnés ci-dessus.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- Suivi des autres recommandations de nos recommandations en matière de réseau : [préparer le réseau de votre organisation aux équipes](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Rubriques connexes

[Principes de connectivité réseau de Microsoft 365 et Office 365](https://aka.ms/pnc)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)
