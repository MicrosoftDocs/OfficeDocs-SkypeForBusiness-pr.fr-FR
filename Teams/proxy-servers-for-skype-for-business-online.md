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
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176671"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Serveurs proxy pour Teams ou Skype Entreprise Online

Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Teams ou Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne teams ou Skype Entreprise le trafic sur les proxys, Microsoft recommande de contourner les proxys. Les proxys ne rendent pas Teams ou Skype Entreprise plus sécurisés, car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes liés aux performances peuvent être introduits dans l’environnement par le biais de la latence et de la perte de paquets en tentant d’acheminer le trafic Teams via un serveur proxy. Les problèmes tels que ceux-ci entraînent une expérience négative dans des scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, où les flux en temps réel sont essentiels.

Nous recommandons que le trafic Teams contourne l’infrastructure du serveur proxy.

## <a name="teams-phones"></a>Téléphones Teams

Les téléphones Teams ne prennent pas en charge les serveurs proxy.

Nous vous recommandons de nous assurer que le trafic de signalisation (TCP 443) et le trafic multimédia (UDP 3478-3481) contourne l’infrastructure du serveur proxy.

## <a name="teams-meeting-rooms-and-panels"></a>Salles de réunion et panneaux Teams

Nous vous recommandons de vous assurer que vos salles de réunion Teams contournent l’infrastructure proxy.

Les salles de réunion Teams windows prennent en charge les serveurs proxy, mais ne prennent pas en charge les serveurs proxy qui nécessitent une authentification. Les salles de réunion Teams basées sur Android ne prennent pas en charge les serveurs proxy.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont pas la possibilité de contourner un proxy pour Teams ou Skype Entreprise le trafic. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.
  
Microsoft recommande également :
  
- Utilisation de la résolution DNS locale externe (certaines solutions de proxy basées sur le cloud peuvent entraîner la résolution DNS à un autre emplacement).
    
- Utilisation d’un routage UDP direct plutôt que de s’appuyer sur le routage tcp pour les médias
    
- Autorisation du trafic UDP (3478-3481)

- Autorisation de toutes les URL et adresses IP requises, y compris celles pour Azure, Office 365, Intune et Teams Room Pro (le cas échéant)
    
- Suivre les autres recommandations de nos recommandations de mise en réseau : [Préparer le réseau de votre organisation pour Teams](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Rubriques connexes

[Principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)
