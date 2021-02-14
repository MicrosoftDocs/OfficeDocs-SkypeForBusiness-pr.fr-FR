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
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec Microsoft Teams ou Skype Entreprise.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665956"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Skype Entreprise Online et Teams

Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Teams ou Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne le trafic Teams ou Skype Entreprise, Microsoft recommande d’éviter d’utiliser un proxies. En raison du chiffrement déjà chiffré, le trafic n’assure pas la sécurité de Teams ou de Skype Entreprise.
  
De plus, le fait d’avoir un proxy peut entraîner des problèmes. Des problèmes de performances peuvent s’introduire dans l’environnement par le biais de la latence et de la perte de paquets. De tels problèmes entraînent une expérience négative dans les scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, pour lequel les flux en temps réel sont essentiels.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont pas d’autres choix que d’utiliser un proxy pour le trafic d’Équipes ou de Skype Entreprise. Si c’est votre cas, vous devez garder à l’esprit les problèmes mentionnés ci-dessus.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- Suivant les autres recommandations de nos directives en matière de mise en réseau : Préparer le réseau de votre [organisation pour Teams](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Sujets associés

[Principes de connectivité réseau de Microsoft 365 et Office 365](https://aka.ms/pnc)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)
