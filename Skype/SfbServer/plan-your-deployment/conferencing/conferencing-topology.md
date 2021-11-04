---
title: Planifier votre topologie de conférence pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: a4d458bf7bea512e773a09551e2fa0c72a982592
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737710"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planifier votre topologie de conférence pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype Entreprise Server.
  
Cette rubrique décrit les principes de base de la topologie pour les conférences dans Skype Entreprise Server :
  
- Topologies prises en charge
    
- Considérations sur les conférences téléphoniques
    
- Considérations sur la conférence web
    
- Conditions requises pour les grandes réunions
    
Pour plus d’informations sur la configuration matérielle et logicielle requise, voir Configuration matérielle et logicielle requise pour les conférences [dans Skype Entreprise Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologies prises en charge

Dans Skype Entreprise Server, le serveur exécutant les services de conférence est toujours coqueté avec les serveurs frontaux ou les serveurs Édition Standard serveurs. Lorsque vous déployez Skype Entreprise Server, les fonctionnalités de conférence par messagerie instantanée sont déployées automatiquement. Vous pouvez spécifier s’il faut déployer la conférence web, audio et vidéo (A/V) et les conférences téléphoniques à l’aide du Générateur de topologie. Vous pouvez également utiliser le Générateur de topologie pour ajouter des conférences à un déploiement existant. Pour plus d’informations sur les principes de base de la topologie et les scénarios de cocation, consultez La base de la [topologie pour Skype Entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Vous pouvez déployer la conférence dans les topologies et configurations suivantes :
  
- Skype Entreprise Server Édition Standard
    
- Skype Entreprise Server Êdition Entreprise
    
- Avec ou sans Voix Entreprise
    
## <a name="dial-in-conferencing-considerations"></a>Considérations sur les conférences téléphoniques

Si vous déployez des conférences téléphoniques, vous devez prendre en compte les considérations suivantes :
  
- La conférence téléphonique nécessite un serveur de médiation pour traduire la signalisation (et les médias dans certaines configurations) entre Skype Entreprise Server et la passerelle PSTN, et une passerelle PSTN pour traduire la signalisation et le média entre le serveur de médiation et la passerelle PSTN.
    
   Avant de pouvoir configurer la conférence téléphonique, vous devez déployer Voix Entreprise ou un serveur de médiation et au moins l’une des configurations suivantes :
    
  - Passerelle PSTN
    
  - IP-PBX
    
  - Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet auquel vous vous connectez en configurant une connexion SIP)
    
- Vous pouvez déployer le service d’application, application Assistant de conférence et application Annonce de conférence sur un site central, mais pas dans un site de succursale.
    
- Vous devez déployer la conférence d’accès dans chaque pool où vous déployez Skype Entreprise Server conférence. Il n’est pas nécessaire d’affecter des numéros d’accès dans chaque pool, mais vous devez déployer la fonctionnalité de conférences téléphoniques dans chaque pool. Cette exigence prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour participer Skype Entreprise Server conférence dans un autre pool. 
    
Pour plus d’informations, voir [Plan for dial-in conferencing in Skype Entreprise Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considérations sur la conférence web

La conférence web nécessite les services suivants : 
  
- Accès au magasin de fichiers, utilisé pour stocker le contenu de conférence web.
    
- Intégration à Office Web Apps Server/Office Online Server, qui est nécessaire pour partager des fichiers PowerPoint pendant une conférence.
    
> [!NOTE]
> La dernière itération de Office Web Apps Server est nommée Office Online Server, qui est prise en charge par Skype Entreprise Server. Pour plus d’informations, reportez-vous [à la documentation Office Online Server.](/officeonlineserver/office-online-server) 
  
Skype Entreprise Server propose les méthodes suivantes pour configurer Office Web Apps Server/Office Online Server. En fonction de vos besoins, vous pouvez :
  
- **Installez Skype Entreprise Server et Office Web Apps Server/Office Online Server local derrière le pare-feu de votre organisation et dans la même zone réseau.** Avec cette topologie, l’accès externe Office Web Apps Server/Office Online Server sera fourni via votre serveur proxy inverse. Dans l’idéal, vous devez installer Office Web Apps Server/Office Online Server dans la même zone réseau que Skype Entreprise Server.
    
    Les clients Skype Entreprise externes peuvent se connecter à Skype Entreprise Server et à Office Web Apps Server/Office Online Server à l’aide d’un serveur proxy inverse, qui est un serveur qui prend les demandes provenant d’Internet et les a transmis au réseau interne. (Les clients internes n’ont pas besoin d’utiliser le serveur proxy inverse, car ils peuvent se connecter Office Web Apps Server/Office Online Server directement.) Cette topologie fonctionne mieux si vous souhaitez utiliser une batterie de serveurs Office Web Apps Server/Office Online Server dédiée qui est utilisée uniquement par les Skype Entreprise Server.
    
- **Utiliser un serveur Web Apps Server/Office déployé en Office Online Server externe.** Dans cette topologie, Skype Entreprise Server est déployé en local et utilise un serveur/Office Online Server Office Web Apps qui est déployé en dehors de la zone réseau Skype Entreprise Server. Cela peut se produire lorsque Office Web Apps Server/Office Online Server est partagé entre plusieurs applications de l’entreprise et est déployé dans un réseau nécessitant Skype Entreprise Server l’utilisation de l’interface externe de Office Web Apps Server/Office Online Server et inversement.
    
    Vous n’avez pas besoin d’installer un serveur proxy inverse ; Au lieu de cela, toutes les demandes du serveur Office Web Apps Server/Office Online Server vers Skype Entreprise Server sont acheminées via votre serveur Edge. Vos clients internes et externes Skype Entreprise se connectent à Office Web Apps Server/Office Online Server l’URL externe.
    
    Si le serveur Office Web Apps Server/Office Online Server est déployé en dehors de votre pare-feu interne, sélectionnez l’option **Office Web Apps Server** est déployé sur un réseau externe (périmètre/Internet) dans le Générateur de topologies.
    
Pour plus d’informations, voir [Configurer l’intégration Office Web Apps Server dans Skype Entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Quelle que soit la topologie que vous sélectionnez, il est essentiel que les ports de pare-feu corrects soient ouverts. Vous devez vous assurer que les noms DNS, les adresses IP et les ports ne sont pas bloqués par des pare-feu sur le serveur/Office Online Server Office Web Apps, l’équilibrage de charge ou le Skype Entreprise Server.
  
> [!NOTE]
> Une autre option permettant de fournir un accès externe à Office Web Apps Server/Office Online Server consiste à déployer le serveur dans le réseau de périmètre. Si vous le souhaitez, n’oubliez pas que le programme d’installation Office Web Apps Server/Office Online Server nécessite que l’ordinateur serveur soit membre de votre domaine Active Directory. À moins que votre stratégie réseau autorise les ordinateurs du réseau de périmètre à être membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server/Office Online Server dans le réseau de périmètre. Au lieu de cela, vous devez installer Office Web Apps Server/Office Online Server dans le réseau interne et fournir aux utilisateurs externes un accès via votre serveur proxy inverse. 
  
## <a name="topology-requirements-for-large-meetings"></a>Exigences en matière de topologie pour les grandes réunions

Une grande réunion nécessite au moins un serveur frontal et un serveur principal. Toutefois, pour fournir une haute disponibilité, nous recommandons un pool de deux serveurs frontux avec des serveurs frontux en miroir, comme illustré dans le diagramme suivant :
  
**Topologie de grandes réunions**

![Topologie de grandes réunions.](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
L’utilisateur qui héberge les grandes réunions doit avoir son compte d’utilisateur dans le pool frontal. Cependant, nous ne recommandons pas que vous hébergiez d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. La meilleure pratique consiste à créer un compte d’utilisateur spécial dans ce pool qui sera utilisé pour héberger les grandes réunions. Étant donné que le paramètre de grande réunion est optimisé pour les performances, son utilisation en tant qu’utilisateur normal peut rencontrer des problèmes tels que l’impossibilité de promouvoir une session P2P en réunion lorsqu’un point de terminaison PSTN est impliqué.
  
La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, voir [Topology Basics for Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
En outre, si vous souhaitez éventuellement fournir la sauvegarde et leover de récupération d’urgence pour le pool utilisé pour les grandes réunions, vous pouvez le jumeler avec un pool dédié de même configurer dans un autre centre de données. Pour plus d’informations, voir [Planifier la haute disponibilité et la récupération d’urgence dans Skype Entreprise Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Autres éléments pour la topologie :
  
- Un partage de fichiers est requis pour le stockage du contenu de la réunion et, si le serveur d’archivage est déployé et activé, pour le stockage des fichiers d’archivage. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du partage de fichiers, voir [Create a file share in Skype Entreprise Server 2015](../../deploy/install/create-a-file-share.md).
    
- Un Office Web Apps Server/Office Online Server est nécessaire pour activer la fonctionnalité PowerPoint présentation dans les grandes réunions. Le serveur Office Web Apps Server/Office Online Server peut être dédié au pool de grandes réunions ou peut être le même serveur Office Web Apps Server/Office Online Server que celui utilisé par d’autres pools sur le site dans lequel le pool dédié est déployé. Pour plus d’informations, voir [Configurer l’intégration Office Web Apps Server dans Skype Entreprise Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- L’équilibrage de charge des serveurs frontux nécessite l’équilibrage de la charge matérielle pour le trafic HTTP (tel que le téléchargement de contenu de réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP. Pour plus [d’informations, voir Les exigences d’équilibrage](../../plan-your-deployment/network-requirements/load-balancing.md)de charge Skype Entreprise . 
    
- Si vous souhaitez utiliser le serveur de surveillance pour le pool dédié aux grandes réunions, nous vous recommandons d’utiliser le serveur de surveillance et sa base de données qui sont partagés entre tous les pools de serveurs frontux dans votre déploiement Skype Entreprise Server. Pour plus d’informations, [voir Planifier la surveillance dans Skype Entreprise Server](../../plan-your-deployment/monitoring.md).
