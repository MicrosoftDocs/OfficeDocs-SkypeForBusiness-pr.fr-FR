---
title: Serveurs proxy pour Skype Entreprise Online et Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Cet article fournit des informations sur l’utilisation d’un serveur proxy avec des équipes ou Skype pour les entreprises.
ms.openlocfilehash: 7ba522e2f49be0ae9846638839193d9c6c3a24b3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465283"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Skype Entreprise Online et Teams

Cet article fournit des instructions sur l’utilisation d’un serveur proxy avec des équipes ou Skype pour les entreprises.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

Lorsqu’il s’agit des équipes ou Skype pour le trafic d’entreprise sur des serveurs proxy, Microsoft vous recommande de contourner les serveurs proxy. Proxys n’apporte des équipes ou Skype pour les entreprises plus sécurisé, car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Problèmes tels que ceux-ci entraînera une expérience négative dans ces équipes ou des Skype pour les scénarios d’entreprise en tant qu’audio et vidéo, où les flux de données en temps réel est essentielles.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont aucune option pour ignorer un proxy pour les équipes ou Skype pour le trafic d’entreprise. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- L'utilisation de la résolution DNS externe
    
- L'utilisation du routage UDP direct
    
- L'autorisation du trafic UDP
    
- Suivant les autres recommandations de nos instructions de mise en réseau :
    
  - [Qualité multimédia et performances de connectivité réseau dans Skype Entreprise Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [Optimisation de votre réseau pour Skype Entreprise Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Rubriques connexes

[Optimisation de votre réseau pour Skype Entreprise Online](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 