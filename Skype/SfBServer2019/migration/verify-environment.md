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
ms.localizationpriority: medium
description: Avant de déployer Skype Entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement hérité avant de déployer un pool pilote Skype Entreprise Server 2019. Avant de déployer XMPP Microsoft Skype Entreprise Server 2019 dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré pris en charge par la configuration XMPP héritée.
ms.openlocfilehash: 208b508eb6b2b5c62da51aa6317cde6e2a95bbb7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727743"
---
# <a name="verify-the-legacy-environment"></a>Vérifier l’environnement hérité

Avant de déployer Skype Entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les principaux services et fonctionnalités qui existent dans votre environnement hérité avant de déployer un pool pilote Skype Entreprise Server 2019. Avant de déployer XMPP Microsoft Skype Entreprise Server 2019 dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré pris en charge par la configuration XMPP héritée. La vérification de votre déploiement hérité implique les choses suivantes :
  
- Vérifier que les services hérités sont démarrés
    
- Examen de la topologie et des utilisateurs
    
- Vérification des paramètres de fédération et de serveur Edge
    
- Vérification des services XMPP et des partenaires fédérés
    
## <a name="verify-that-legacy-services-are-started"></a>Vérifier que les services hérités sont démarrés

1. À partir du serveur frontal hérité, accédez à l’applet Outils d’administration\Services.
    
2. Vérifiez que les services suivants sont exécutés sur le serveur frontal :
    
     ![Liste des services en cours d’exécution sur le serveur frontal.](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Examiner la topologie héritée dans le Skype Entreprise Server de contrôle

1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez Skype Entreprise Server panneau de bord.
    
3. Sélectionnez **Topologie**. Vérifiez que les différents serveurs de votre déploiement hérité sont répertoriés.
    
     ![Page topologie du Panneau de contrôle.](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Passer en revue les utilisateurs hérités dans le Skype Entreprise Server de contrôle

1. Ouvrez Skype Entreprise Server panneau de bord.
    
2. Sélectionnez **Utilisateurs,** puis cliquez sur **Rechercher.**
    
3. Vérifiez que la colonne **Pool de** bureaux d’inscriptions pointe vers le pool hérité pour chaque utilisateur répertorié. 
    
     ![Panneau de contrôle répertoriant les utilisateurs.](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Vérifier les paramètres edge et de fédération hérités

1. Démarrez le Générateur de topologie.
    
2. Sélectionnez **Télécharger la topologie à partir du déploiement existant**.
    
3. Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier .tbxml par défaut.
    
4. Développez le nœud d’installation hérité pour révéler les différents rôles serveur dans le déploiement.
    
5. Sélectionnez le nœud de site et vérifiez qu’une valeur d’affectation **d’itinéraire de fédération de** site est définie. 
    
     ![Générateur de topologie, itinéraire de fédération de site.](../media/migration_lyncserver_w14_federation.jpg)
  
6. Sélectionnez le Édition Standard serveur ou Êdition Entreprise pool frontal. Déterminez si un pool edge a été configuré pour les médias sous **Associations.** 
    
     ![Générateur de topologie affichant les serveurs et les pools.](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Sélectionnez le pool edge et identifiez si un pool du saut suivant est configuré sous **la sélection du saut suivant.**
    
     ![Générateur de topologie, sélection du saut suivant.](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Vérifier la configuration des partenaires fédérés XMPP hérités

1. À partir du serveur XMPP hérité, naviguez vers l’applet Outils/Services d’administration.
    
2. Vérifiez que le service de passerelle XMPP Office Communications Server est démarré. 
    
     ![Office Service de passerelle XMPP Communications Server.](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

