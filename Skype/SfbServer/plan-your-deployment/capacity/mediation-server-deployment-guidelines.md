---
title: Instructions de déploiement pour le serveur de médiation dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Cette rubrique décrit les instructions de planification pour le déploiement du serveur de médiation.
ms.openlocfilehash: 1a35d2f0bb74cfd78cba8924e6cafb6ce601d647
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228452"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a>Instructions de déploiement pour le serveur de médiation dans Skype pour Business Server
 
Cette rubrique décrit les instructions de planification pour le déploiement du serveur de médiation.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation colocalisé ou autonome ?

Serveur de médiation, par défaut, colocalisé sur le serveur Standard Edition server ou un serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels sur le réseau téléphonique commuté (RTC) pouvant être gérés et le nombre d’ordinateurs nécessaires dans le pool dépendront :
  
- Le nombre d’homologues de passerelle que le pool de serveur de médiation contrôle.
    
- des périodes de trafic aux heures de pointe sur ces passerelles ;
    
- Pourcentage d’appels qui contournent le serveur de médiation.
    
Lors de la planification, n’oubliez de tenir compte de la configuration de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurées pour la déviation du trafic multimédia, ainsi que du traitement nécessaire à la gestion des interactions de signalisation des nombreux appels devant être pris en charge aux heures de pointe. Si vous ne disposez pas suffisamment UC, vous devez déployer un pool de serveurs de médiation autonome. En outre, les passerelles PSTN, PBX IP et SBC devrez devant résulter de sous-ensembles sont contrôlés par les serveurs de médiation colocalisé dans un pool et les serveurs de médiation autonome dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles PSTN, IP-PBX ou des contrôleurs de frontière de Session (SBC) qui ne possèdent pas la possibilité d’interagir avec un pool de serveurs de médiation, ils devrez être associé à un pool autonome constitué d’un seul serveur de médiation. Vos passerelles RTC, systèmes IP-PBX ou contrôleurs SBC doivent bénéficier des éléments suivants :
  
- Effectuer le nom de domaine DNS (Domain Name System) équilibrage entre les serveurs de médiation dans un pool de la couche réseau (ou acheminer le trafic de manière uniforme sur tous les serveurs de médiation dans un pool).
    
- Accepter le trafic à partir de n’importe quel serveur de médiation dans un pool.
    
Vous pouvez utiliser la Skype pour l’outil de planification d’entreprise à évaluer si colocaliser le serveur de médiation avec votre pool frontal peut gérer la charge. Si votre environnement ne peut pas ces exigences, vous devrez déployer un pool de serveur de médiation autonome.
  
## <a name="central-site-and-branch-site-considerations"></a>Aspects relatifs au site central et aux sites de succursale

 Serveurs de médiation sur le site central peuvent servir à acheminer les appels pour IP-PBX ou des passerelles PSTN au niveau des sites de succursale. Toutefois, si vous déployez les jonctions SIP, vous devez déployer un serveur de médiation au niveau du site dans lequel chaque jonction se termine. Un serveur de médiation sur le site central acheminer des appels pour un IP-PBX ou passerelle PSTN sur un site de succursale ne nécessite pas l’utilisation de supports de contournement, mais un le contournement de média est recommandé. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès du trafic multimédia et bénéficier ainsi d’une meilleure qualité du trafic multimédia, car le chemin d’accès au contenu multimédia n’est plus nécessaire pour suivre le chemin de signalisation. La déviation du trafic multimédia réduira également la charge de traitement sur le pool.
  
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et contrôleur SBC. Microsoft a testé plusieurs passerelles RTC et contrôleurs SBC en collaboration avec des partenaires agréés et a effectué différents tests avec les systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et les versions répertoriés dans Unified Communications programme Open Interoperability - Lync Server à [Explorer testé appareils, infrastructure et outils qui prennent en charge et étendent votre Skype pour une expérience](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si la résilience de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal, un serveur de médiation et une passerelle doit être déployé sur le site de succursale. (En partant du principe avec résilience de site de succursale est que de présence et de conférence ne sont pas résistantes au niveau du site.) Pour obtenir des instructions sur le site de succursale planification de voix, voir [Plan for Enterprise Voice resiliency dans Skype pour Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).
  
Pour interagir avec un PBX IP, si le système IP-PBX ne prend pas correctement en charge les interactions multimédias au plus tôt avec plusieurs boîtes de dialogue préliminaires et interactions RFC 3960, il peut y avoir écrêtage du premier premiers mots du message d’accueil pour les appels entrants à partir de l’IP-PBX aux points de terminaison Lync. Ce problème peut être plus grave si un serveur de médiation sur un site central est routage des appels pour un IP-PBX où l’itinéraire s’arrête sur un site de succursale, car davantage de temps est nécessaire pour la signalisation à effectuer. Si vous rencontrez ce problème, déployez un serveur de médiation sur le site de succursale est la seule façon de réduire le découpage de la première premiers mots.
  
Enfin, si votre site central a un système PBX TDM, ou si votre système IP-PBX n’élimine pas la nécessité d’une passerelle PSTN, vous devez déployer une passerelle sur l’itinéraire d’appel de connexion du serveur de médiation et le système PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, voir «[Améliorations de mise à l’échelle côté réception dans Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)». Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau. 
  

