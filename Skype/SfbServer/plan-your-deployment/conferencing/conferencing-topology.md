---
title: Planification de votre topologie de conférence pour Skype entreprise Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Résumé : consultez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype entreprise Server.'
ms.openlocfilehash: 68ee859979deb7d977ee546e711474d0b6ba06e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030778"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planification de votre topologie de conférence pour Skype entreprise Server
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype entreprise Server.
  
Cette rubrique décrit les concepts de base de la topologie pour les conférences dans Skype entreprise Server :
  
- Topologies prises en charge
    
- Considérations relatives à la Conférence rendez-vous
    
- Considérations relatives à la conférence Web
    
- Conditions requises pour les grandes réunions
    
Pour plus d’informations sur la configuration matérielle et logicielle requise, voir [Hardware and Software Requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologies prises en charge

Dans Skype entreprise Server, le serveur exécutant les services de conférence est toujours colocalisé avec les serveurs frontaux ou les serveurs Standard Edition. Lorsque vous déployez Skype entreprise Server, les fonctionnalités de conférence par messagerie instantanée sont déployées automatiquement. Vous pouvez spécifier s’il faut déployer le Web, l’audio et la vidéo (A/V) et la Conférence rendez-vous à l’aide du générateur de topologie. Vous pouvez également utiliser le générateur de topologie pour ajouter des conférences à un déploiement existant. Pour plus d’informations sur les concepts de base de la topologie et les scénarios de colocalisation, voir [Topology concepts for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Vous pouvez déployer la Conférence dans les topologies et configurations suivantes :
  
- Skype entreprise Server Standard Edition
    
- Skype entreprise Server Enterprise Edition
    
- Avec ou sans voix entreprise
    
## <a name="dial-in-conferencing-considerations"></a>Considérations relatives à la Conférence rendez-vous

Si vous déployez la Conférence rendez-vous, vous devez tenir compte des éléments suivants :
  
- La Conférence rendez-vous nécessite un serveur de médiation pour traduire la signalisation (et les médias dans certaines configurations) entre Skype entreprise Server et la passerelle PSTN, ainsi qu’une passerelle PSTN pour traduire la signalisation et les médias entre le serveur de médiation et la passerelle PSTN. .
    
   Avant de pouvoir configurer la Conférence rendez-vous, vous devez déployer voix entreprise ou un serveur de médiation et au moins l’un des éléments suivants :
    
  - Passerelle PSTN
    
  - IP-PBX
    
  - Contrôleur de frontière de session (SBC) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une jonction SIP)
    
- Vous pouvez déployer le service d’application, l’application de surveillance de conférence et l’application d’annonce de conférence dans un site central, mais pas dans un site de succursale.
    
- Vous devez déployer la Conférence rendez-vous dans chaque pool où vous déployez Skype entreprise Server Conferencing. Vous n’avez pas besoin d’attribuer des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool. Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre une conférence Skype entreprise Server dans un autre pool. 
    
Pour plus d’informations, reportez-vous à la rubrique [plan for Dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considérations relatives à la conférence Web

La conférence Web nécessite les éléments suivants : 
  
- Accès au magasin de fichiers, utilisé pour le stockage du contenu de conférence Web.
    
- Intégration à Office Web Apps Server/Office Online Server, ce qui est nécessaire pour partager des fichiers PowerPoint pendant une conférence.
    
> [!NOTE]
> La dernière itération d’Office Web Apps Server est appelée Office Online Server, qui est pris en charge par Skype entreprise Server. Pour plus d’informations, reportez-vous à la [documentation d’Office Online Server](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
Skype entreprise Server fournit les méthodes suivantes pour configurer Office Web Apps Server/Office Online Server. En fonction de vos besoins, vous pouvez :
  
- **Installez Skype entreprise Server et Office Web Apps Server/Office Online Server en local derrière le pare-feu de votre organisation et dans la même zone réseau.** Avec cette topologie, l’accès externe au serveur Office Web Apps Server/Office Online Server sera fourni par le biais de votre serveur proxy inverse. Idéalement, vous devez installer Office Web Apps Server/Office Online Server dans la même zone de réseau que Skype entreprise Server.
    
    Les clients Skype entreprise externes peuvent se connecter à Skype entreprise Server et à Office Web Apps Server/Office Online Server à l’aide d’un serveur proxy inverse, qui est un serveur qui prend des demandes en provenance d’Internet et les transmet au réseau interne. (Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à Office Web Apps Server/Office Online Server.) Cette topologie est idéale si vous voulez utiliser une batterie de serveurs Office Web Apps Server/Office Online Server dédiée qui est utilisée uniquement par Skype entreprise Server.
    
- **Utiliser un serveur Office Web Apps Server/Office Online Server déployé en externe.** Dans cette topologie, Skype entreprise Server est déployé localement et utilise un serveur Office Web Apps Server/Office Online Server déployé en dehors de la zone réseau de Skype entreprise Server. Cela peut se produire lorsque Office Web Apps Server/Office Online Server est partagé entre plusieurs applications au sein de l’entreprise et déployé dans un réseau requérant que Skype entreprise Server utilise l’interface externe d’Office Web Apps Server/Office Online Server et inversement.
    
    Il n’est pas nécessaire d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes provenant du serveur Office Web Apps Server/Office Online Server vers Skype entreprise Server sont acheminées via votre serveur Edge. Vos clients Skype entreprise internes et externes se connectent à Office Web Apps Server/Office Online Server à l’aide de l’URL externe.
    
    Si Office Web Apps Server/Office Online Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option le **serveur Office Web Apps Server est déployé sur un réseau externe** (périmètre/Internet) dans le générateur de topologie.
    
Pour plus d’informations, consultez la rubrique [configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Quelle que soit la topologie que vous sélectionnez, il est essentiel que les ports de pare-feu appropriés soient ouverts. Vous devez vous assurer que les noms DNS, les adresses IP et les ports ne sont pas bloqués par des pare-feu sur le serveur Office Web Apps Server/Office Online Server, l’équilibreur de charge ou Skype entreprise Server.
  
> [!NOTE]
> Une autre option permettant de fournir un accès externe au serveur Office Web Apps Server/Office Online Server consiste à déployer le serveur dans le réseau de périmètre. Si vous choisissez de le faire, n’oubliez pas que le programme d’installation d’Office Web Apps Server/Office Online Server requiert que l’ordinateur serveur soit membre de votre domaine Active Directory. À moins que votre stratégie réseau ne permette aux ordinateurs du réseau de périmètre d’être des membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server/Office Online Server dans le réseau de périmètre. Au lieu de cela, vous devez installer Office Web Apps Server/Office Online Server dans le réseau interne et fournir l’accès des utilisateurs externes par le biais de votre serveur proxy inverse. 
  
## <a name="topology-requirements-for-large-meetings"></a>Exigences de topologie pour les grandes réunions

Une seule réunion de grande taille nécessite au moins un serveur frontal et un serveur principal. Toutefois, pour assurer une haute disponibilité, nous vous recommandons d’utiliser un pool de serveurs frontaux mis en miroir, comme illustré dans le diagramme suivant :
  
**Topologie de réunion de grande taille**

![Topologie de réunion de grande taille](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Le compte d’utilisateur de l’utilisateur qui héberge les grandes réunions doit être hébergé dans un pool frontal. Cependant, nous ne recommandons pas que vous hébergiez d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. La meilleure pratique consiste à créer un compte d’utilisateur spécial dans ce pool qui sera utilisé pour héberger les grandes réunions. Étant donné que le paramètre de réunion de grande taille est optimisé pour les performances, son utilisation en tant qu’utilisateur normal pourrait avoir des problèmes tels que l’impossibilité de promouvoir une session P2P pour une réunion lorsqu’un point de terminaison PSTN est impliqué.
  
La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, voir [concepts de base de la topologie pour Skype entreprise server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) et [topologies de référence pour skype entreprise Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
En outre, si vous souhaitez éventuellement fournir une sauvegarde et un basculement de récupération d’urgence pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un pool dédié configuré de la même manière dans un autre centre de données. Pour plus d’informations, reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Autres éléments pour la topologie :
  
- Un partage de fichiers est requis pour le stockage du contenu de la réunion et, si le serveur d’archivage est déployé et activé, pour le stockage des fichiers d’archivage. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du partage de fichiers, voir [Create a File Share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Office Web Apps Server/Office Online Server est nécessaire pour activer la fonctionnalité de présentation PowerPoint dans les grandes réunions. Office Web Apps Server/Office Online Server peut être dédié au pool de réunions de grande taille ou il peut s’agir du même serveur Office Web Apps Server/Office Online Server utilisé par d’autres pools au niveau du site dans lequel le pool dédié est déployé. Pour plus d’informations, consultez la rubrique [configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de la charge matérielle pour le trafic HTTP (par exemple, le téléchargement de contenu de réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP. Pour plus d’informations, voir [Load Balancing Requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Si vous souhaitez utiliser le serveur de surveillance pour le pool dédié aux grandes réunions, nous vous recommandons d’utiliser le serveur de surveillance et sa base de données qui sont partagés sur tous les pools de serveurs frontaux dans votre déploiement Skype entreprise Server. Pour plus d’informations, reportez-vous à la rubrique [plan for Monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

