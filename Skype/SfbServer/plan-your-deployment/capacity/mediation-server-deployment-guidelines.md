---
title: Instructions de déploiement du serveur de médiation dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: Cette rubrique décrit les directives de planification pour le déploiement du serveur de médiation.
ms.openlocfilehash: e1017e9fab43578fd3c10e8043c7dcc747d313b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server-2015"></a>Instructions de déploiement du serveur de médiation dans Skype Entreprise Server 2015
 
Cette rubrique décrit les directives de planification pour le déploiement du serveur de médiation.
  
## <a name="collocated-or-stand-alone-mediation-server"></a>Serveur de médiation colocalisé ou autonome ?

Serveur de médiation est, par défaut, colocalisé sur le serveur Standard Edition server ou un serveur frontal dans un pool frontal sur les sites centraux. Le nombre d’appels sur le réseau téléphonique commuté (RTC) pouvant être gérés et le nombre d’ordinateurs nécessaires dans le pool dépendront :
  
- Le nombre de pairs de passerelle contrôlant le pool de serveur de médiation.
    
- des périodes de trafic aux heures de pointe sur ces passerelles ;
    
- Pourcentage d’appels appels dont media ignore le serveur de médiation.
    
Lors de la planification, n’oubliez de tenir compte de la configuration de traitement multimédia pour les appels RTC et les conférences A/V qui ne sont pas configurées pour la déviation du trafic multimédia, ainsi que du traitement nécessaire à la gestion des interactions de signalisation des nombreux appels devant être pris en charge aux heures de pointe. Si vous n’avez pas suffisamment UC, vous devrez déployer un pool autonome de serveurs de médiation. En outre, les passerelles RTPC, IP-PBX et SBCs devrez diviser en sous-ensembles qui sont contrôlées par les serveurs de médiation colocalisée dans un pool et les serveurs de médiation autonome dans un ou plusieurs pools autonomes.
  
Si vous avez déployé des passerelles RTPC, IP-PBX ou des contrôleurs de bordure de Session (SBCs) qui ne disposent pas de la possibilité d’interagir avec un pool de serveurs de médiation, ils devez être associé à un pool autonome consistant en un seul serveur de médiation. Vos passerelles RTC, systèmes IP-PBX ou contrôleurs SBC doivent bénéficier des éléments suivants :
  
- Effectuer la couche réseau nom de domaine (DNS) répartition des charges sur les serveurs de médiation dans un pool (ou sinon router le trafic uniformément à tous les serveurs de médiation dans un pool).
    
- Accepter le trafic à partir de n’importe quel serveur de médiation dans un pool.
    
Vous pouvez utiliser le Microsoft Lync Server 2013, outil de planification pour évaluer si COLLOCATION avec votre pool frontal, le serveur de médiation peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devrez déployer un pool de serveur de médiation autonome.
  
## <a name="central-site-and-branch-site-considerations"></a>Considérations relatives au site central et aux sites de succursale

 Des serveurs de médiation sur le site central peuvent être utilisés pour acheminer les appels pour IP-PBX ou passerelles RTPC sur les sites des succursales. Toutefois, si vous déployez les trunks SIP, vous devez déployer un serveur de médiation sur le site où chaque ligne se termine. Un serveur de médiation sur le site central itinéraire appelle un IP-PBX ou passerelle PSTN à un site de la succursale ne nécessite pas l’utilisation de médias contourner, mais un contournement de média est recommandé. Cependant, si vous pouvez l’activer, vous pourrez réduire la latence du chemin d’accès du trafic multimédia et bénéficier ainsi d’une meilleure qualité du trafic multimédia, car le chemin d’accès au contenu multimédia n’est plus nécessaire pour suivre le chemin de signalisation. La déviation du trafic multimédia réduira également la charge de traitement sur le pool.
  
> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC, système IP-PBX et contrôleur SBC. Microsoft a testé plusieurs passerelles RTC et contrôleurs SBC en collaboration avec des partenaires agréés et a effectué différents tests avec les systèmes IP-PBX de Cisco. Le contournement de média est pris en charge uniquement avec les produits et versions répertoriées sur Unified Communications Ouvrir programme d’interopérabilité - Lync Server à [Explorer testé périphériques, infrastructure et les outils qui prennent en charge et d’étendre votre Skype pour une expérience](http://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
Si la résilience de site de succursale est requise, un Survivable Branch Appliance ou une combinaison d’un serveur frontal et un serveur de médiation, une passerelle doit être déployé sur le site de la succursale. (La prise en charge avec la résilience de site de succursale est que présence et les conférences ne sont pas résilientes sur le site.) Pour obtenir des instructions sur le site de la succursale de planification pour la voix, consultez notre documentation de [planification pour le Site de la succursale la résilience vocale](https://technet.microsoft.com/en-us/library/gg398477%28v=ocs.15%29.aspx) , tel qu’il doit toujours être pertinente pour Skype pour Business Server 2015.
  
Pour les interactions avec un PBX IP, si l’IP-PBX ne gère pas correctement anticipée interactions media avec plusieurs boîtes de dialogue précoces et des interactions de la RFC 3960, il est possible d’écrêtage des premiers mots de la carte de vœux pour les appels entrants à partir de l’IP-PBX aux points de terminaison de Lync. Ce problème peut être plus grave si un serveur de médiation dans un site central est acheminement d’appels pour un IP-PBX où l’itinéraire met fin à un site de la succursale, car plus de temps est nécessaire pour la signalisation terminer. Si vous rencontrez ce problème, déployez un serveur de médiation au site de la succursale est la seule façon de réduire l’écrêtage du premier peu de mots.
  
Enfin, si votre site central a un PBX TDM, ou si votre PBX IP n’élimine pas la nécessité d’une passerelle RTPC, vous devez déployer une passerelle sur l’itinéraire de l’appel de connexion de serveur de médiation et le PBX.
  
> [!NOTE]
> Pour améliorer les performances multimédias d’un serveur de médiation autonome, activez RSS (Receive-Side Scaling) sur les cartes réseau de ces serveurs. RSS permet la gestion en parallèle des paquets entrants par plusieurs processeurs sur le serveur. Pour plus d’informations, consultez «[Améliorations de mise à l’échelle côté réception dans Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)». Pour plus d’informations sur l’activation de RSS, reportez-vous à la documentation de votre carte réseau. 
  

