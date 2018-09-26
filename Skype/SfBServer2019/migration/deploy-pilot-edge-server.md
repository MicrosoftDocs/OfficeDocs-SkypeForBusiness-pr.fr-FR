---
title: Déployer le serveur Edge pilote
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre Skype pour Business Server 2019 Edge Server. Les processus de déploiement et configuration pour Skype pour Business Server 2019 sont très similaires aux Skype pour Business Server 2015. Cette section met en évidence uniquement les points clés que vous devez prendre en compte dans le cadre de votre déploiement du pool pilote. Pour obtenir la procédure détaillée, consultez Déploiement de l’accès des utilisateurs externes dans Skype pour Business Server 2019 dans la documentation de déploiement, qui décrit le processus de déploiement et fournit également des informations de configuration pour l’accès des utilisateurs externes.
ms.openlocfilehash: 3ae1508c56ac3240cfb9904415090ff1bdf18677
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029859"
---
# <a name="deploy-pilot-edge-server"></a>Déployer le serveur Edge pilote

Cette rubrique présente les paramètres de configuration que vous devez connaître avant de déployer votre Skype pour Business Server 2019 Edge Server. Les processus de déploiement et configuration pour Skype pour Business Server 2019 sont très similaires aux Skype pour Business Server 2015. Cette section met en évidence uniquement les points clés que vous devez prendre en compte dans le cadre de votre déploiement du pool pilote. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
Lorsque vous naviguez dans l’Assistant **Définir un nouveau Pool Edge** , passez en revue les paramètres de configuration de la clé indiqués dans les étapes suivantes. Notez que seuls quelques pages de l’Assistant **Définir un nouveau Pool Edge** sont affichées. 
  
### <a name="to-define-an-edge-pool"></a>Pour définir un Pool de serveurs Edge

1. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    
2. Accédez à la Skype Business Server 2019 nœud. **Pools de serveurs Edge**d’avec le bouton droit, puis cliquez sur **pool de serveurs Edge de nouveau**.
    
     ![Définir la boîte de dialogue Nouveau Pool Edge](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Un pool Edge peut être un **pool de plusieurs ordinateurs** ou un **seul ordinateur**.
    
     ![Définir la boîte de dialogue Nom complet du Pool de serveur Edge](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. Dans la page **Sélectionner les fonctionnalités** , n’activez pas la fédération ou la fédération XMPP. Fédération et la fédération XMPP sont les deux actuellement acheminés via le serveur Edge hérité. Ces fonctionnalités vont être configurées dans une phase ultérieure de la migration. 

  
5. Continuez à remplir les pages suivantes de l’Assistant : **Noms de domaine complets externes**, **définir l’adresse IP interne**et **définir l’adresse IP externe**.
    
6. Dans la page **définir le serveur du tronçon suivant** , sélectionnez le directeur pour le tronçon suivant du pool Edge hérité. 
    
     ![Définir la boîte de dialogue tronçon suivant](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. Dans la page **associer Front-End ou des pools de médiation** , n’associez pas un pool à ce pool Edge à ce stade. Le trafic multimédia externe n’est actuellement routé via le serveur Edge hérité. Ce paramètre de configuration dans une phase ultérieure de la migration. 
    
     ![Associer la boîte de dialogue Pools frontaux](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. Cliquez sur **Terminer**, puis sur **Publier** la topologie. 
    
9. Suivez les étapes décrites dans la documentation de déploiement pour installer les fichiers sur le nouveau serveur de périphérie, configurer des certificats et démarrer les services. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
Il est très important que vous suivez les instructions fournies dans les rubriques de la documentation de déploiement. Cette section fournie simplement des conseils sur les paramètres de configuration lors de l’installation de ces rôles de serveur. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
Vous devez voir apparaître un serveur Edge hérité déployés en parallèle avec un Skype pour un déploiement de serveur Edge Server 2019 Business server. Vérifiez que les deux déploiements fonctionnent correctement, les services sont démarrés et vous pouvez administrer chaque déploiement avant de passer à la phase suivante. 
  

