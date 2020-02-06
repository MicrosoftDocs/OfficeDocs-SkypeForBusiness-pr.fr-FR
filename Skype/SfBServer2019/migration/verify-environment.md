---
title: Vérifier l’environnement hérité
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité, avant de déployer un pool de pilotes Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré qui utilise la configuration XMPP héritée. annexes.
ms.openlocfilehash: 34c9ecbc4fe9863c09b2648145ff46c1628ef655
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812692"
---
# <a name="verify-the-legacy-environment"></a>Vérifier l’environnement hérité

Avant de déployer Skype entreprise Server 2019 dans un état de coexistence, vous devez vérifier que les services hérités ont été configurés et démarrés. Il est important d’identifier les services et fonctionnalités clés qui existent dans votre environnement hérité avant de déployer un pool de pilotes Skype entreprise Server 2019. Avant de déployer Microsoft Skype entreprise Server 2019 XMPP dans un état de coexistence avec un déploiement XMPP hérité, vous devez vérifier que les services XMPP hérités ont été configurés et démarrés, et identifier le partenaire fédéré de la fonction XMPP héritée. la configuration est prise en charge. La vérification de votre déploiement hérité implique les éléments suivants :
  
- Vérification du démarrage des services hérités
    
- Examen de la topologie et des utilisateurs
    
- Vérification des paramètres de serveur de Fédération et de périphérie
    
- Vérification des services XMPP et des partenaires fédérés
    
## <a name="verify-that-legacy-services-are-started"></a>Vérifier la mise en route des services hérités

1. À partir du serveur frontal antérieur, accédez à l’applet d’administration Tools\Services.
    
2. Vérifiez que les services suivants s’exécutent sur le serveur frontal :
    
     ![Liste des services s’exécutant sur un serveur frontal](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a>Passer en revue la topologie héritée dans le panneau de configuration Skype entreprise Server

1. Ouvrez une session sur le serveur frontal avec un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’admistrateur CsAdministrator ou CsUserAdministrator.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Sélectionnez **topologie**. Vérifiez que les différents serveurs dans votre déploiement hérité sont répertoriés.
    
     ![Page Topology du panneau de configuration](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a>Examiner les anciens utilisateurs dans le panneau de configuration Skype entreprise Server

1. Ouvrez le panneau de configuration Skype entreprise Server.
    
2. Sélectionnez **utilisateurs**, puis cliquez sur **Rechercher**.
    
3. Vérifiez que la colonne **pool d’inscriptions** pointe vers le pool hérité de chaque utilisateur répertorié. 
    
     ![Liste des utilisateurs dans le panneau de configuration](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a>Vérifier les paramètres de bord et de Fédération hérités

1. Démarrer le générateur de topologie.
    
2. Sélectionnez **Télécharger la topologie à partir du déploiement existant**.
    
3. Choisissez un nom de fichier et enregistrez la topologie avec le type de fichier default. tbxml.
    
4. Développez le nœud installations héritées pour afficher les différents rôles serveur du déploiement.
    
5. Sélectionnez le nœud site et vérifiez qu’une valeur d’attribution de l' **itinéraire de Fédération de site** est définie. 
    
     ![Générateur de topologie, itinéraire de Fédération de site](../media/migration_lyncserver_w14_federation.jpg)
  
6. Sélectionnez la liste frontale Standard Edition Server ou Enterprise Edition. Déterminez s’il est configuré pour le contenu multimédia inférieur aux **associations**. 
    
     ![Générateur de topologie affichant des serveurs et des groupes](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. Sélectionnez le pool de bords et déterminez si un pool de prochains tronçons est configuré en dessous de l' **option tronçon suivant**.
    
     ![Générateur de topologie, sélection du tronçon suivant](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a>Vérification de la configuration de partenaire fédéré hérité de XMPP

1. À partir du serveur XMPP hérité, accédez à l’applet d’administration Tools\Services.
    
2. Vérifiez que le service de passerelle XMPP d’Office Communications Server est démarré. 
    
     ![Service de passerelle Office Communications Server XMPP](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

