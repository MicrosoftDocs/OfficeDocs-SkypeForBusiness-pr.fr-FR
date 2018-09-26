---
title: Vérification de l’environnement hérité
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Avant de déployer Skype pour Business Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement hérité, avant de déployer un Skype pour le pool pilote Business Server 2019. Avant de déployer Microsoft Skype pour Business Server 2019 XMPP dans un état de la coexistence avec un déploiement XMPP hérité, vous devez vérifier les services XMPP hérités ont été configurés et démarrés et identifier les partenaires fédérés est la configuration XMPP héritée prise en charge.
ms.openlocfilehash: d6e4585e127009117345d1220458196b5b461b6a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030426"
---
# <a name="verify-the-legacy-environment"></a>Vérification de l’environnement hérité

Avant de déployer Skype pour Business Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement avant de déployer un Skype pour le pool pilote Business Server 2019 hérité. Avant de déployer Microsoft Skype pour Business Server 2019 XMPP dans un état de la coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés et identifier qui partenaire les XMPP hérité fédéré prise en charge de la configuration. Vérification de votre déploiement hérité implique les tâches suivantes :
  
- Vérification que les services hérités sont démarrés.
    
- Examen de la topologie et les utilisateurs
    
- Vérification de la fédération et les paramètres du serveur Edge
    
- Vérification des services XMPP et des partenaires fédérés
    
## <a name="verify-that-legacy-services-are-started"></a>Vérifiez que les services hérités sont démarrés

1. Hérité serveur frontal, accédez à l’applet outils d’administration.
    
2. Vérifiez que les services suivants sont en cours d’exécution sur le serveur frontal :
    
     ![Liste des services s’exécutant sur le serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Passez en revue la topologie héritée dans Skype pour Business Server Control Panel

1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez le Skype pour le panneau de configuration serveur Business.
    
3. Sélectionnez **la topologie**. Vérifiez que les différents serveurs dans votre déploiement hérité sont répertoriés.
    
     ![Page de la topologie du Panneau de configuration de contrôle](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Passez en revue les utilisateurs hérités dans Skype pour Business Server Control Panel

1. Ouvrez le Skype pour le panneau de configuration serveur Business.
    
2. Sélectionnez **les utilisateurs**, puis cliquez sur **Rechercher**.
    
3. Vérifiez que la colonne **Pool de serveurs d’inscriptions** pointe vers le pool hérité pour chaque utilisateur répertorié. 
    
     ![Le panneau de configuration répertoriant les utilisateurs](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Vérifiez les paramètres de fédération et Edge hérités

1. Démarrez le Générateur de topologie.
    
2. Sélectionnez **Télécharger la topologie à partir du déploiement existant**.
    
3. Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.
    
4. Développez le nœud installe hérité pour afficher les différents rôles de serveur dans le déploiement.
    
5. Sélectionnez le nœud du site et vérifiez qu’une valeur de **l’attribution itinéraire de fédération du Site** est définie. 
    
     ![Générateur de topologies, itinéraire de fédération de Site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Sélectionnez le pool frontal Standard Edition Server ou Enterprise Edition. Déterminer si un pool de serveurs Edge a été configuré pour le média sous **Associations**. 
    
     ![Générateur de topologie indiquant les serveurs et pools](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Sélectionnez le pool Edge et déterminer si un pool du tronçon suivant est configuré sous **sélection du tronçon suivant**.
    
     ![Sélection du tronçon suivant du Générateur de topologie](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Vérifiez le partenaire fédéré XMPP hérité Configuration

1. Le serveur XMPP hérité, accédez à l’applet outils d’administration.
    
2. Vérifiez que le service de passerelle XMPP de Office Communications Server est démarré. 
    
     ![Service de passerelle XMPP Office Communications Server](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

