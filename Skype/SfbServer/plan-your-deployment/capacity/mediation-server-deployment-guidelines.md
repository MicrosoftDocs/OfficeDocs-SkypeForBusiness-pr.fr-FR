---
title: Recommandations en matière de déploiement pour le serveur de médiation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Cette rubrique décrit les recommandations en matière de planification pour le déploiement de médiation Server.
ms.openlocfilehash: 806886b7c7c5e8ae367a6e104f7fd9127f25c099
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816053"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Recommandations en matière de déploiement pour le serveur de médiation dans Skype entreprise Server
 
Cette rubrique décrit les recommandations en matière de planification pour le déploiement de médiation Server.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation autonome ou colocalisé

Le serveur de médiation est par défaut colocalisé sur le serveur Standard Edition Server ou serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels sur le réseau téléphonique commuté (RTC) pouvant être gérés et le nombre d’ordinateurs nécessaires dans le pool dépendront :
  
- Nombre d’homologues de passerelle qu’il contrôle.
    
- des périodes de trafic aux heures de pointe sur ces passerelles ;
    
- Pourcentage d’appels pour lesquels le média de contournement du serveur de médiation est ignoré.
    
Lors de la planification, n’oubliez de tenir compte de la configuration de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurées pour la déviation du trafic multimédia, ainsi que du traitement nécessaire à la gestion des interactions de signalisation des nombreux appels devant être pris en charge aux heures de pointe. Si vous n’avez pas suffisamment d’UC, vous devez déployer un pool autonome de serveurs de médiation. De plus, les passerelles RTC, les PBX IP et SBCs doivent être divisées en sous-ensembles contrôlés par les serveurs de médiation colocalisés d’un pool et de serveurs de médiation autonomes dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles RTC, des PBX IP ou des contrôleurs de frontière de session (SBCs) qui n’ont pas la possibilité d’interagir avec une réserve de serveurs de médiation, ils doivent être associés à un pool autonome composé d’un serveur de médiation unique. Vos passerelles RTC, systèmes IP-PBX ou contrôleurs SBC doivent bénéficier des éléments suivants :
  
- Effectue l’équilibrage de charge DNS (Layer Domain Name System) sur les serveurs de médiation d’un pool (ou d’acheminer uniformément le trafic sur tous les serveurs de médiation d’un pool).
    
- Accepter le trafic de n’importe quel serveur de médiation dans un pool.
    
Vous pouvez utiliser l’outil de planification de Skype pour les entreprises pour déterminer si collocating du serveur de médiation avec votre pool frontal, peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.
  
## <a name="central-site-and-branch-site-considerations"></a>Aspects relatifs au site central et aux sites de succursale

 Les serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels pour les PBX IP ou les passerelles RTC dans les sites de succursale. Toutefois, si vous déployez des Trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque Trunk est arrêté. Le fait de disposer d’un serveur de médiation au niveau du site central pour les appels pour un PBX IP ou une passerelle RTC sur un site de succursale ne nécessite pas l’utilisation du contournement du contenu multimédia, mais une dérivation multimédia est recommandée. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès du trafic multimédia et bénéficier ainsi d’une meilleure qualité du trafic multimédia, car le chemin d’accès au contenu multimédia n’est plus nécessaire pour suivre le chemin de signalisation. La déviation du trafic multimédia réduira également la charge de traitement sur le pool.
  
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et contrôleur SBC. Microsoft a testé plusieurs passerelles RTC et contrôleurs SBC en collaboration avec des partenaires agréés et a effectué différents tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server dans [Explorer les appareils, l’infrastructure et les outils testés qui prennent en charge et étendront votre interface Skype entreprise](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si la résilience du site de succursale est requise, il est nécessaire d’avoir une branche ou une combinaison d’un serveur frontal, d’un serveur de médiation et d’une passerelle dans le site de succursale. (L’hypothèse de la résilience du site de succursale est que la présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des instructions sur la planification du site de succursale pour les appels vocaux, voir [planifier la résilience vocale d’entreprise dans Skype entreprise Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
S’il s’agit d’interactions avec un PBX IP, si ce n’est 3960 pas le cas, vous pouvez découper les premiers mots du message d’accueil pour les appels entrants du PBX IP vers les points de terminaison de Lync. Ce comportement peut être plus sérieux si un serveur de médiation sur un site central effectue le routage des appels pour un PBX IP à l’endroit où l’itinéraire se termine sur un site de succursale, car une plus grande période est nécessaire pour que le signalement s’exécute. Si vous subissez ce comportement, le déploiement d’un serveur de médiation sur le site de la succursale est le seul moyen de réduire l’écrêtage des premiers mots.
  
Enfin, si votre site central possède un PBX TDM ou si votre PBX IP n’élimine pas la nécessité d’une passerelle RTC, vous devez déployer une passerelle sur l’itinéraire d’appel connexion du serveur de médiation et du PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez la section «[améliorations apportées à l’échelle de réception dans Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)». Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau. 
  

