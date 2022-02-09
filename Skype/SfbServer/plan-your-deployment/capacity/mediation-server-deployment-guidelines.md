---
title: Instructions de déploiement pour le serveur de médiation dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Cette rubrique décrit les instructions de planification pour le déploiement du serveur de médiation.
ms.openlocfilehash: 1b5f628f544cafb358b58d325c5d077aef783a89
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397618"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Instructions de déploiement pour le serveur de médiation dans Skype Entreprise Server
 
Cette rubrique décrit les instructions de planification pour le déploiement du serveur de médiation.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation c colloté ou autonome ?

Par défaut, le serveur de médiation est coqueté sur le serveur Édition Standard serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels PSTN (réseau téléphonique commuté) qui peuvent être gérés et le nombre d’ordinateurs requis dans le pool dépendent des facteurs ci-après :
  
- Nombre d’homologues de passerelle que contrôle le pool de serveurs de médiation.
    
- Périodes de trafic à volume élevé via ces passerelles.
    
- Pourcentage d’appels dont le média contourne le serveur de médiation.
    
Lors de la planification, n’oubliez pas de prendre en compte les exigences de traitement multimédia pour les appels PSTN et les conférences A/V qui ne prennent pas en charge le contournement de média, ainsi que le traitement nécessaire pour gérer les interactions de signalisation pour le nombre d’appels aux heures de pointe qui doivent être pris en charge. Si vous n’avez pas assez de processeur, vous devez déployer un pool autonome de serveurs de médiation. En outre, les passerelles PSTN, les SYSTÈMES IP-PBX et les SCS doivent être divisés en sous-ensembles contrôlés par les serveurs de médiation cococérés dans un pool et les serveurs de médiation autonomes dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles PSTN, des PBX IP ou des contrôleurs de frontière de session (SDC) qui n’ont pas la possibilité d’interagir avec un pool de serveurs de médiation, ils doivent être associés à un pool autonome constitué d’un serveur de médiation unique. Voici quelques-unes des choses que vos passerelles PSTN, IP-PBXs ou SCS doivent faire :
  
- Effectuer l’équilibrage de charge DNS (Domain Name System) de couche réseau sur les serveurs de médiation dans un pool (ou router le trafic de manière uniforme vers tous les serveurs de médiation d’un pool).
    
- Acceptez le trafic provenant de n’importe quel serveur de médiation d’un pool.
    
Vous pouvez utiliser l’Skype Entreprise de planification pour déterminer si la cococation du serveur de médiation avec votre pool frontal peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.
  
## <a name="central-site-and-branch-site-considerations"></a>Considérations relatives au site central et aux sites de succursale

 Les serveurs de médiation sur le site central peuvent être utilisés pour router les appels sur les sites de succursale pour les passerelles PSTN ou les IP-PBX. Toutefois, si vous déployez des trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque trunk s’termine. L’utilisation d’un serveur de médiation sur le site central route les appels pour un SYSTÈME IP-PBX ou une passerelle PSTN sur un site de succursale ne nécessite pas l’utilisation du contournement de média, mais un contournement de média est recommandé. En effet, si vous pouvez activer le contournement de média, cela réduit la latence du chemin d’accès du média et, par conséquent, améliore la qualité des médias, car le chemin d’accès du média n’est pas requis pour suivre le chemin de signalisation. Le contournement de média réduira également la charge de traitement sur le pool.
  
> [!NOTE]
> Le contournement de média ne fonctionne pas avec toutes les passerelles PSTN, IP-PBX et SBC. Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec des PBX IP Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriés dans le programme Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype Entreprise experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si la résistance de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle doit être déployé sur le site de succursale. (L’hypothèse avec la résilience de site de succursale est que la présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des conseils sur la planification des sites de succursale pour la voix, voir [Plan for Voix Entreprise resiliency in Skype Entreprise Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Pour les interactions avec un IP-PBX, si le PBX IP ne prend pas correctement en charge les interactions multimédias précoces avec plusieurs boîtes de dialogue anticipées et les interactions RFC 3960, il peut y avoir un découpage des premiers mots du message d’accueil pour les appels entrants du PBX IP vers les points de terminaison Lync. Ce comportement peut s’aggraver si un serveur de médiation sur le site central achemine les appels pour un IP-PBX là où s’arrête l’itinéraire sur un site de succursale, car la signalisation a besoin de plus de temps pour se terminer. Si vous faites l’expérience de ce comportement, le déploiement d’un serveur de médiation sur le site de succursale est le seul moyen de réduire le découpage des premiers mots.
  
Pour finir, si votre site central comporte un TDM PBX ou que votre IP-PBX ne supprime pas le besoin d’une passerelle PSTN, vous devez alors déployer une passerelle sur l’itinéraire d’appel qui se connecte au serveur de médiation et au PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias du serveur de médiation autonome, vous devez activer la mise à l’échelle côté réception (RSS) sur les cartes réseau sur ces serveurs. RSS permet de gérer les paquets entrants en parallèle à l’aide de plusieurs processeurs sur le serveur. Pour plus d’informations, voir [« Receive-Side Scaling Enhancements in Windows Server](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh997036(v=ws.11)) ». Pour plus d’informations sur l’activer, consultez la documentation de votre carte réseau. 
