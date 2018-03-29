---
title: Planification d’une topologie de conférence pour Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype pour Business Server 2015.'
ms.openlocfilehash: b81a8eeb1300fa6bad887ba923c28fc4d2676fe8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server-2015"></a>Planification d’une topologie de conférence pour Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur la planification de votre topologie de conférence dans Skype pour Business Server 2015.
  
Cette rubrique décrit les aspects fondamentaux de la topologie pour les conférences dans Skype Entreprise Server 2015 :
  
- Topologies prises en charge
    
- Aspects relatifs aux conférences rendez-vous
    
- Aspects relatifs aux conférences web
    
- Configuration requise pour les réunions importantes
    
Pour plus d’informations sur la configuration matérielle et logicielle, voir [configuration matérielle et logicielle pour les conférences dans Skype pour Business Server 2015](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologies prises en charge

Dans Skype pour Business Server, le serveur exécutant les services de conférence est toujours colocalisé avec les serveurs de serveurs frontaux ou Standard Edition. Lorsque vous déployez Skype pour Business Server, les capacités de conférence par messagerie instantanée sont déployées automatiquement. Vous pouvez choisir de déployer ou non les fonctionnalités de conférence web, audio et vidéo (A/V) et de conférence rendez-vous à l’aide du générateur de topologie. Vous pouvez également utiliser le générateur de topologie pour ajouter la fonction de conférence à un déploiement existant. Pour plus d’informations sur les concepts de topologie et de colocalisation scénarios, consultez [Notions fondamentales de topologie pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Vous pouvez déployer des conférences dans les topologies et les configurations suivantes :
  
- Skype pour Business Server Standard Edition
    
- Skype pour Business Server Édition entreprise
    
- Avec ou sans Voix Entreprise
    
## <a name="dial-in-conferencing-considerations"></a>Aspects relatifs aux conférences rendez-vous

Si vous déployez une conférence rendez-vous, vous devez prendre en compte les éléments suivants :
  
-  Conférences à distance nécessite un serveur de médiation pour traduire de signalisation (et les supports dans certaines configurations) entre Skype pour Business Server la passerelle RTC et une passerelle RTPC pour traduire de signalisation et multimédias entre le serveur de médiation et la passerelle RTC .
    
    Avant de pouvoir configurer la conférence rendez-vous, vous devez déployer Voix Entreprise ou un serveur de médiation et au moins l’une des ressources suivantes :
    
  - Passerelle RTC
    
  - IP-PBX
    
  - Contrôleur SBC (Session Border Controller) (pour un fournisseur de services de téléphonie Internet sur lequel vous vous connectez en configurant une jonction SIP [Session Initiation Protocol])
    
- Vous pouvez déployer le service d’application, l’application Intendant Conférence et l’application Annonce de conférence sur un site central, mais pas sur un site de succursale.
    
- Vous devez déployer à distance conférence dans chaque pool où vous déployez Skype pour les conférences de Business Server. Il n’est pas nécessaire d’attribuer des numéros d’accès à chaque pool, mais vous devez déployer la fonctionnalité de conférence rendez-vous dans chaque pool. Cette condition prend en charge la fonctionnalité de nom enregistré lorsqu’un utilisateur appelle un numéro d’accès à partir d’un pool pour joindre un Skype pour la conférence Business Server dans un autre pool. 
    
Pour plus d’informations, reportez-vous à la section [planifier la conférence à distance dans Skype pour Business Server 2015](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Aspects relatifs aux conférences web

Les conférences web nécessitent les actions suivantes : 
  
- Accès au magasin de fichiers permettant de stocker le contenu des conférences web
    
- Intégration au serveur Office Web Apps Server/Office Online Server nécessaire au partage de fichiers PowerPoint lors d’une conférence.
    
> [!NOTE]
> La dernière itération d’Office Web Apps Server nommée Office en ligne, qui est pris en charge par Skype pour Business Server 2015. Pour plus de détails, reportez-vous à la [documentation du serveur en ligne de Office](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype pour Business Server fournit les méthodes suivantes pour configurer Office Web Apps serveur/Office Server en ligne. En fonction de vos besoins, vous pouvez :
  
- **Installez les deux Skype pour Business Server et le serveur en ligne pour Office Web Apps Server/bureau local derrière le pare-feu de votre organisation et dans la même zone du réseau.** Avec cette topologie, l’accès externe au serveur Office Web Apps Server/Office Online Server sera fourni par le biais de votre serveur proxy inverse. Dans l’idéal, vous devez installer Office Web Apps serveur/Office Server en ligne dans la même zone de réseau que Skype pour Business Server.
    
    Skype externe pour les clients d’entreprise peut se connecter à Skype pour Business Server et Office Web Apps serveur/Office Server en ligne en utilisant un serveur proxy inverse, qui est un serveur qui accepte les demandes provenant d’Internet et les transfère vers le réseau interne. (Les clients internes est inutile d’utiliser le serveur proxy inverse, car ils peuvent se connecter directement à un serveur en ligne pour Office Web Apps serveur/Office.) Cette topologie fonctionne mieux si vous souhaitez utiliser une batterie de serveur en ligne pour Office Web Apps/Office de serveur dédiée qui est uniquement utilisée par Skype pour Business Server.
    
- **Utilisez un déployé en externe Office Web Apps serveur/Office serveur en ligne.** Dans cette topologie, Skype pour Business Server est déployé sur site et utilise un serveur Web Office applications serveur/Office en ligne qui est déployé en dehors de la Skype pour une zone réseau de serveur d’entreprise. Cela peut se produire lorsque le serveur en ligne pour Office Web Apps serveur/Office est partagé entre plusieurs applications de l’entreprise et est déployé dans un réseau nécessitant le Skype pour Business Server utiliser l’interface externe du serveur en ligne pour Office Web Apps serveur/Office et vice versa.
    
    Vous n’avez pas besoin d’installer un serveur proxy inverse ; au lieu de cela, toutes les demandes du serveur en ligne Office Web Apps Server/Bureau à Skype pour Business Server sont acheminés par l’intermédiaire de votre serveur de transport Edge. Interne et votre Skype externe pour les clients de l’entreprise de se connectent à Office Web Apps serveur/Office serveur en ligne à l’aide de l’URL externe.
    
    Si le serveur Office Web Apps Server/Office Online Server est déployé à l’extérieur de votre pare-feu interne, sélectionnez l’option **Le serveur Office Web Apps est déployé sur un réseau externe (périmètre/Internet)** dans le générateur de topologie.
    
Pour plus d’informations, consultez [configurer une intégration avec Office Web Apps Server dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Indépendamment de la topologie sélectionnée, les ports de pare-feu corrects doivent absolument être ouverts. Il se peut que vous devez vous assurer que les noms DNS, les adresses IP et les ports ne sont pas bloqués par un pare-feu sur le serveur Office Web Apps serveur/Office en ligne, l’équilibrage de la charge ou Skype pour Business Server.
  
> [!NOTE]
> Une autre option permettant de fournir un accès externe au serveur Office Web Apps Server/Office Online Server consiste à déployer le serveur dans le réseau de périmètre. Si vous sélectionnez cette option, n’oubliez pas que pour installer Office Web Apps Server/Office Online Server, l’ordinateur serveur doit être membre de votre domaine Active Directory. Sauf si votre stratégie de réseau autorise les ordinateurs du réseau de périmètre à être des membres du domaine Active Directory, il est recommandé de ne pas installer Office Web Apps Server/Office Online Server dans le réseau de périmètre. Installez plutôt Office Web Apps Server/Office Online Server dans le réseau interne et fournissez un accès utilisateur externe par le biais de votre serveur de proxy inverse.  
  
## <a name="topology-requirements-for-large-meetings"></a>Configuration de la topologie requise pour les grandes réunions

Une grande réunion nécessite au moins un serveur frontal et un serveur principal. Cependant, pour fournir une haute disponibilité, nous recommandons un pool de serveurs frontaux avec des serveurs principaux en miroir, comme sur le diagramme suivant :
  
**Topologie de la réunion**

![Topologie de réunions importantes](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
Le compte de l’utilisateur qui héberge les grandes réunions doit être hébergé dans ce pool frontal. Cependant, nous ne recommandons d’héberger d’autres comptes d’utilisateur dans ce pool. Utilisez-le uniquement pour les grandes réunions. Il est recommandé de créer un compte d’utilisateur spécial dans ce pool, qui ne sera utilisé que pour héberger les grandes réunions. Étant donné que le paramètre des grandes réunions est optimisé pour les performances, son utilisation en tant qu’utilisateur normal peut entraîner des problèmes, comme une incapacité à promouvoir une session P2P dans une réunion lorsqu’un point de terminaison RTC est impliqué.
  
La gestion d’un pool avec deux serveurs frontaux nécessite une attention particulière. Pour plus d’informations, consultez [Bases de topologie Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) et [topologies de référence pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
De plus, si vous voulez fournir la sauvegarde de récupération d’urgence et le basculement pour le pool utilisé pour les grandes réunions, vous pouvez l’associer à un autre pool dédié configuré de la même façon dans d’autres centres de données. Pour plus d’informations, consultez [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Remarques supplémentaires sur la topologie sont les suivants :
  
- Un partage de fichiers est nécessaire pour le stockage du contenu de la réunion et, si Archiving Server est déployé et activé, pour le stockage des fichiers d’archive. Le partage de fichiers peut être dédié au pool ou peut être le même que celui utilisé par un autre pool du site dans lequel le pool est déployé. Pour plus d’informations sur la configuration du partage de fichiers, reportez-vous à la section [créer un partage de fichiers dans Skype pour Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Un serveur Office Web Apps Server/Office Online Server est nécessaire pour permettre la fonctionnalité de présentation PowerPoint dans les grandes réunions. Un serveur Office Web Apps Server/Office Online Server peut être dédié au pool de grandes réunions ou peut être le même serveur Office Web Apps Server/Office Online Server que celui utilisé par les autres pools du site dans lequel le pool dédié est déployé. Pour plus d’informations, consultez [configurer une intégration avec Office Web Apps Server dans Skype pour Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- L’équilibrage de charge des serveurs frontaux nécessite l’équilibrage de charge matérielle pour le trafic HTTP (le téléchargement de contenu de la réunion). L’équilibrage de charge DNS est recommandé pour le trafic SIP (Session Initiation Protocol). Pour plus d’informations, voir [équilibrage de la charge requise pour Skype pour les entreprises](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Si vous souhaitez utiliser Monitoring Server pour le pool de grande réunion dédié, nous vous recommandons d’à l’aide du serveur de surveillance et de sa base de données qui sont partagées entre tous les pools de serveur frontal dans votre Skype pour le déploiement du serveur de l’entreprise. Pour plus d’informations, consultez le [Plan de surveillance dans Skype pour Business Server 2015](../../plan-your-deployment/monitoring.md).
    

