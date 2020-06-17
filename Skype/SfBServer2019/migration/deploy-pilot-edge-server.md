---
title: Déploiement d’un serveur Edge pilote
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
description: Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype entreprise Server 2019. Les processus de déploiement et de configuration de Skype entreprise Server 2019 sont très similaires à ceux de Skype entreprise Server 2015. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour obtenir la procédure détaillée, voir Deploying External User Access in Skype for Business Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752866"
---
# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype entreprise Server 2019. Les processus de déploiement et de configuration de Skype entreprise Server 2019 sont très similaires à ceux de Skype entreprise Server 2015. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown. 
  
### <a name="to-define-an-edge-pool"></a>Pour définir un pool de serveurs Edge

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
2. Accédez au nœud Skype entreprise Server 2019. Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.
    
     ![Boîte de dialogue définir le nouveau pool Edge](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.
    
     ![Boîte de dialogue définir le nom de domaine complet du pool Edge](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP. Fédération et la Fédération XMPP sont actuellement routées via le serveur Edge hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration. 

  
5. Continuez à remplir les pages suivantes de l’Assistant : noms de **domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.
    
6. Sur la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool de serveurs de périphérie hérité. 
    
     ![Boîte de dialogue définir le tronçon suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Dans la page **associer des pools frontaux ou des pools de médiation** , n’associez pas un pool à ce pool Edge pour le moment. Le trafic multimédia externe est actuellement routé via le serveur Edge hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration. 
    
     ![Boîte de dialogue pools frontaux associés](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Cliquez sur **Terminer**, puis **publiez** la topologie. 
    
9. Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Il est très important de suivre les instructions des rubriques de la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Un serveur Edge hérité doit maintenant être déployé en parallèle avec un déploiement de serveur Edge Skype entreprise Server 2019. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante. 
  

