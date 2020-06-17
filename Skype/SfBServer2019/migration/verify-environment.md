---
title: Vérifier l’environnement hérité
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool pilote Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée.
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751676"
---
# <a name="verify-the-legacy-environment"></a>Vérifier l’environnement hérité

Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et les fonctionnalités clés qui existent dans votre environnement hérité avant de déployer un pool pilote Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui prend en charge la configuration XMPP héritée. La vérification de votre déploiement hérité implique les éléments suivants :
  
- Vérification du démarrage des services hérités
    
- Examen de la topologie et des utilisateurs
    
- Vérification des paramètres de Fédération et du serveur Edge
    
- Vérification des services XMPP et des partenaires fédérés
    
## <a name="verify-that-legacy-services-are-started"></a>Vérifier que les services hérités sont démarrés

1. À partir du serveur frontal hérité, accédez à l’applet Administration\services. d’administration.
    
2. Vérifiez que les services suivants sont exécutés sur le serveur frontal :
    
     ![Liste des services exécutés sur un serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Examiner la topologie héritée dans le panneau de configuration de Skype entreprise Server

1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez le panneau de configuration de Skype entreprise Server.
    
3. Sélectionnez **Topologie**. Vérifiez que les différents serveurs de votre déploiement hérité sont répertoriés.
    
     ![Page topologie du panneau de configuration](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Examiner les utilisateurs hérités dans le panneau de configuration de Skype entreprise Server

1. Ouvrez le panneau de configuration de Skype entreprise Server.
    
2. Sélectionnez **utilisateurs**, puis cliquez sur **Rechercher**.
    
3. Vérifiez que la colonne pool de serveurs d' **inscriptions** pointe vers le pool hérité pour chaque utilisateur mentionné. 
    
     ![Liste des utilisateurs dans le panneau de configuration](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Vérifier les paramètres de serveur Edge et de Fédération hérités

1. Démarrez le Générateur de topologie.
    
2. Sélectionnez **Télécharger la topologie à partir du déploiement existant**.
    
3. Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.
    
4. Développez le nœud installations héritées pour afficher les différents rôles serveur dans le déploiement.
    
5. Sélectionnez le nœud de site et vérifiez qu’une valeur d’attribution de l' **itinéraire de Fédération du site** est définie. 
    
     ![Générateur de topologies, itinéraire de Fédération du site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Sélectionnez le serveur Standard Edition ou le pool frontal Enterprise Edition. Déterminez si un pool de serveurs Edge a été configuré pour les médias sous les **associations**. 
    
     ![Générateur de topologies affichant les serveurs et les pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Sélectionnez le pool de serveurs Edge et déterminez si un pool de tronçons suivant est configuré en dessous de **sélection du tronçon suivant**.
    
     ![Générateur de topologies, sélection du tronçon suivant](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Vérifier la configuration des partenaires fédérés XMPP hérités

1. À partir du serveur XMPP hérité, naviguez vers l’applet Outils/Services d’administration.
    
2. Vérifiez que le service de passerelle XMPP Office Communications Server est démarré. 
    
     ![Service de passerelle XMPP Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

