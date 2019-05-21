---
title: Déploiement d’un serveur Edge pilote
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge 2019 Skype entreprise Server. Le processus de déploiement et de configuration de Skype entreprise Server 2019 est très similaire à celui de Skype entreprise Server 2015. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. Pour plus d’informations, reportez-vous à la rubrique déploiement d’un accès utilisateur externe dans Skype entreprise Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280916"
---
# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

Cette rubrique présente les paramètres de configuration que vous devez prendre en compte avant de déployer votre serveur Edge 2019 Skype entreprise Server. Le processus de déploiement et de configuration de Skype entreprise Server 2019 est très similaire à celui de Skype entreprise Server 2015. Cette section présente uniquement les points clés à prendre en compte dans le cadre de votre déploiement de pool pilote. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
À mesure que vous parcourez l’Assistant **définir un nouveau pool de bords** , passez en revue les paramètres de configuration clés indiqués dans les étapes suivantes. Notez que seules quelques pages de l’Assistant **définir un nouveau pool de bords** sont affichées. 
  
### <a name="to-define-an-edge-pool"></a>Pour définir un pool de bords

1. Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.
    
2. Accédez au nœud Skype entreprise Server 2019. Cliquez avec le bouton droit sur pools de **bords**, puis cliquez sur **nouvelle liste de bord**.
    
     ![Boîte de dialogue définir la nouvelle réserve de bords](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool Edge peut être un pool d' **ordinateurs** ou un **pool d’ordinateurs unique**.
    
     ![Définir la boîte de dialogue nom de domaine complet du pool de bords](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Dans la page **Sélectionner des fonctionnalités** , n’activez pas la Fédération de Fédération ou XMPP. Les fédérations de Fédération et XMPP sont actuellement routées via le serveur Edge hérité. Ces fonctionnalités seront configurées lors de la phase de migration ultérieure. 

  
5. Continuez à remplir les pages suivantes de l’Assistant: noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.
    
6. Dans la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de bords antérieurs. 
    
     ![Boîte de dialogue définir le saut suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Dans la page **Associate front end ou pools de médiation** , n’associez pas un pool à ce pool d’arêtes pour le moment. Le trafic de médias externes est actuellement acheminé via le serveur Edge hérité. Ce paramètre sera configuré lors de la phase de migration ultérieure. 
    
     ![Boîte de dialogue Associate](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Cliquez sur **Terminer**, puis **publiez** la topologie. 
    
9. Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer des certificats et démarrer les services. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Il est très important de suivre les recommandations des rubriques de la documentation de déploiement. Cette section fournit uniquement des recommandations en matière de paramètres de configuration lors de l’installation de ces rôles de serveur. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Vous devez maintenant disposer d’un serveur Edge hérité déployé en parallèle avec un déploiement de serveur Edge Skype entreprise Server 2019. Vérifiez que les deux déploiements s’exécutent correctement, que les services sont démarrés et que vous pouvez gérer chaque déploiement avant de passer à la phase suivante. 
  

