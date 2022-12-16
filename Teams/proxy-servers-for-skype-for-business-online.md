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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436680"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Serveurs proxy pour Teams et Skype Entreprise Online

Cet article fournit des conseils sur l’utilisation d’un serveur proxy avec Teams ou Skype Entreprise.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Il est déconseillé d'utiliser un serveur proxy.

En ce qui concerne teams ou Skype Entreprise le trafic sur les proxys, Microsoft recommande de contourner les proxys. Les proxys ne rendent pas Teams ou Skype Entreprise plus sécurisés, car le trafic est déjà chiffré.
  
De plus, un serveur proxy peut entraîner des complications. Des problèmes liés aux performances peuvent être introduits dans l’environnement par le biais de la latence et de la perte de paquets en tentant d’acheminer le trafic Teams via un serveur proxy. Les problèmes tels que ceux-ci entraînent une expérience négative dans des scénarios Teams ou Skype Entreprise tels que l’audio et la vidéo, où les flux en temps réel sont essentiels.

Nous recommandons que le trafic Teams contourne l’infrastructure du serveur proxy. Vous souhaiterez peut-être y parvenir en plaçant les téléphones Teams et les appareils de salle de réunion sur leur propre réseau local virtuel et en leur fournissant un accès à Internet.

## <a name="windows-based-teams-devices"></a>appareils Windows-Based Teams

Les salles de réunion Teams windows et les Surface Hubs prennent en charge certains serveurs proxy, mais ne prennent pas en charge les serveurs proxy qui nécessitent une authentification.

Nous vous recommandons de contourner votre infrastructure proxy et d’accéder Microsoft services 365 via votre pare-feu.

## <a name="android-based-teams-devices"></a>appareils Android-Based Teams

Les appareils Teams android, y compris les téléphones, les panneaux, les écrans et les tableaux Teams, ne prennent pas en charge les serveurs proxy.

En raison de la façon dont certains composants s’exécutant sur ces appareils accèdent à Internet, il n’est pas possible d’acheminer tout le trafic via un proxy. Vous devez vous assurer que le trafic entre ces appareils et Microsoft services 365 est autorisé via votre pare-feu.

## <a name="if-you-need-to-use-a-proxy-server"></a>SI vous devez utiliser un serveur proxy

Certaines organisations n’ont pas la possibilité de contourner un proxy pour Teams ou Skype Entreprise le trafic. Si cela est votre cas, rappelez-vous des problèmes mentionnés plus haut.

> [!Note]
> Si vous utilisez un certificat signé en privé sur votre infrastructure proxy, vous devez installer le certificat signé en privé et la chaîne de certificats sur l’appareil de salle de réunion Teams pour permettre à l’appareil d’approuver le certificat. L’installation de certificats signés en privé sur les téléphones Teams et d’autres appareils Teams android n’est pas prise en charge.
  
Microsoft recommande également :
  
- Utilisation de la résolution DNS locale externe (certaines solutions de proxy basées sur le cloud peuvent entraîner la résolution DNS à un autre emplacement).

- S’assurer que le chemin entre l’appareil Teams et notre service est aussi court et direct que possible
    
- Utilisation d’un routage UDP direct plutôt que de s’appuyer sur le routage tcp pour les médias
    
- Autorisation du trafic UDP pour Teams Media (3478-3481) via votre pare-feu

- Autorisation de toutes les URL et adresses IP requises, y compris celles pour Azure, Office 365, Intune et Teams Room Pro (le cas échéant) via votre pare-feu
    
- Suivre les autres recommandations de nos recommandations de mise en réseau : [Préparer le réseau de votre organisation pour Teams](prepare-network.md)
  
    
Ces conseils devraient limiter l'apparition de problèmes.
  
## <a name="related-topics"></a>Rubriques connexes

[Principes de connectivité réseau de Microsoft 365 et Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)
