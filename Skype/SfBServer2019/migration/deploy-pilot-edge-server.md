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
ms.localizationpriority: medium
description: Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype Entreprise Server 2019. Les processus de déploiement et de configuration Skype Entreprise Server 2019 sont très similaires à Skype Entreprise Server 2015. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. Pour obtenir la procédure détaillée, voir Déploiement de l’accès des utilisateurs externes dans Skype Entreprise Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: 39ec659c5099a7be9587c630aa487ddeda1df500
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728043"
---
# <a name="deploy-pilot-edge-server"></a>Déploiement d’un serveur Edge pilote

Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre serveur Edge Skype Entreprise Server 2019. Les processus de déploiement et de configuration Skype Entreprise Server 2019 sont très similaires à Skype Entreprise Server 2015. Cette section présente uniquement les points clés dont vous devez tenir compte dans le cadre du déploiement de votre pool pilote. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
À mesure que vous parcourez l’Assistant **Définir un nouveau pool Edge**, examinez les principaux paramètres de configuration mentionnés aux étapes suivantes. Notez que seules quelques pages de l’Assistant **Définir un nouveau pool Edge** sont illustrées. 
  
### <a name="to-define-an-edge-pool"></a>Pour définir un pool edge

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.
    
2. Accédez au nœud Skype Entreprise Server 2019. Cliquez avec le bouton droit sur **Pools Edge**, puis cliquez sur **Nouveau pool de serveurs Edge**.
    
     ![Définissez la boîte de dialogue Nouveau pool edge.](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **pool d’un seul ordinateur**.
    
     ![Définissez la boîte de dialogue FQDN du pool edge.](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Dans la page **Sélectionner les fonctionnalités**, n’activez pas la fédération ni la fédération XMPP. La fédération et la fédération XMPP sont actuellement acheminées via le serveur Edge hérité. Ces fonctionnalités seront configurées lors d’une phase ultérieure de la migration. 

  
5. Continuez à compléter les pages de l’Assistant suivantes : **Les FQDN externes,** définissez l’adresse **IP** interne et définissez **l’adresse IP externe.**
    
6. Dans la page **Définir le serveur du saut suivant,** sélectionnez le directeur pour le saut suivant du pool Edge hérité. 
    
     ![Définissez la boîte de dialogue Saut suivant.](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Dans la page **Associer un pool frontal** ou un pool de médiation, n’associez pas de pool à ce pool edge pour le moment. Le trafic multimédia externe est actuellement acheminé via le serveur Edge hérité. Ce paramètre sera configuré lors d’une phase ultérieure de la migration. 
    
     ![Boîte de dialogue Associer des pools frontux.](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Cliquez **sur** Terminer, puis **publiez** la topologie. 
    
9. Suivez les étapes de la documentation de déploiement pour installer les fichiers sur le nouveau serveur Edge, configurer les certificats et démarrer les services. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Il est très important de suivre les instructions des rubriques de la documentation de déploiement. Cette section ne fait que fournir des recommandations concernant les paramètres de configuration lors de l’installation de ces rôles de serveur. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Vous devez maintenant avoir un serveur Edge hérité déployé en parallèle avec un déploiement de Skype Entreprise Server Edge 2019. Vérifiez que les deux déploiements fonctionnent correctement, que les services ont démarré et que vous pouvez administrer chaque déploiement avant de passer à la phase suivante. 
  

