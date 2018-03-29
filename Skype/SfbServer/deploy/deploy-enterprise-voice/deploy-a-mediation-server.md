---
title: Déploiement d’un serveur de médiation dans le générateur de topologie dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Apprenez à les définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015.'
ms.openlocfilehash: bfb915528ba73851d3bd60cc8ff3b33b968376e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server-2015"></a>Déploiement d’un serveur de médiation dans le générateur de topologie dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à les définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server 2015.
  
La charge de travail de Voix Entreprise, conférence à distance avancées Voix Entreprise des applications et (application de groupe réponse, application d’appel Park, contrôle admission des appels (CAC) et ainsi de suite), sont disponibles dans les pools de Front-End. La fonctionnalité du serveur de médiation est intégrée dans le serveur frontal. Un serveur de médiation autonome distinct n’est pas nécessaire. 
  
La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour vous connecter à votre infrastructure de Voix Entreprise à votre fournisseur de jonction SIP, un serveur de médiation distincte doit être déployé.
  
La connexion entre Skype pour Business Server (soit un serveur de médiation concernant un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée un trunk. Les rubriques de cette section décrivent comment définir un tronc et comment déployer un serveur de médiation autonome, si vous vous connectez à un SIP trunk.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Définition d’un serveur de médiation dans le générateur de topologie

Vous pouvez ajouter un serveur de médiation en tant que colocalisé rôle sur un pool frontal, ou définir un autonome pool de serveur de médiation.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation pour un pool frontal

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.
    
2. Dans le Générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.
    
3. Dans l’arborescence de la console, cliquez sur le type de pool frontal que vous voulez, puis cliquez sur **Nouveau Front End pool..**.
    
4. Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.
    
5. Dans **rôles de Select server colocalisé**, cochez l’option **Serveur de médiation colocaliser**.
    
    > [!NOTE]
    > Si le type de pool frontal que vous avez sélectionné est la version Enterprise Edition, le composant serveur de médiation va être installé sur tous les serveurs frontaux de ce pool de Front-End. 
  
    > [!NOTE]
    > Le **pool du tronçon suivant** utilisé par le serveur de médiation sera le pool frontal où le serveur de médiation se trouve sur.
  
    > [!NOTE]
    > Le **pool de bord** utilisé par le serveur de médiation sera le même pool de bord associé au pool frontal où le serveur de médiation se trouve sur.
  
6. Cliquez sur **Utiliser par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le RTC.
    
7. Cliquez sur **Terminer** lorsque vous avez terminé l’association d’un ou plusieurs collègues au pool de Front-End.
    
    > [!NOTE]
    > Avant de passer à l’étape suivante dans le processus de déploiement de Voix Entreprise, assurez-vous que le pool de serveur de médiation (c'est-à-dire Front-End colocalisé de pool avec le composant serveur de médiation) utilise les noms de domaine complets que vous avez spécifié. 
  
8. Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Pour ajouter un serveur de médiation autonome

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.
    
2. Dans le Générateur de topologies, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.
    
3. Dans l’arborescence de la console, cliquez sur le nœud **pools de médiation** , puis cliquez sur **pool de serveur de médiation**.
    
4. **Définir un nouveau Pool de médiation**, tapez le nom de domaine pleinement qualifié (FQDN) du pool serveur de médiation.
    
5. Effectuez ensuite l’une des opérations suivantes :
    
   - Si vous souhaitez déployer plusieurs serveurs de médiation dans le pool pour fournir une haute disponibilité, puis sélectionnez **plusieurs pool d’ordinateur**.
    
    > [!NOTE]
    > Vous devez déployer (... /.. / plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveur de médiation qui ont plusieurs serveurs de médiation.
  
   - Si vous souhaitez ne déployer qu’un seul serveur de médiation dans le pool, car vous n’avez pas besoin de haute disponibilité, puis sélectionnez le **pool d’un seul ordinateur**. Ignorez l’étape suivante.
    
6. Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter à la liste. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.
    
7. Dans la page **Sélectionnez le tronçon suivant** , cliquez sur **pool du tronçon suivant**, cliquez sur le nom de domaine complet du pool Front-End qui utilisent ce pool de serveur de médiation, puis cliquez sur **suivant**.
    
8. Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
   - Si vous souhaitez fournir la connectivité RTPC aux utilisateurs externes de Voix Entreprise, sous **Sélectionnez le Pool bord utilisé par ce serveur de médiation**, cliquez sur le nom de domaine complet du pool de serveur de transport Edge qui utilisera ce pool de serveur de médiation pour assurer la connectivité RTPC les utilisateurs externes, puis cliquez sur **suivant**.
    
   - Si vous ne souhaitez pas permettre aux utilisateurs externes de Voix Entreprise, ou si vous ne souhaitez pas fournir la connectivité RTPC aux utilisateurs lorsqu’ils sont en dehors du réseau interne, cliquez sur **suivant**.
    
9. Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Définir les Ports à l’écoute de serveur de médiation

Suivez les étapes de cette rubrique pour utiliser le Générateur de topologies pour définir les ports d’écoute à un serveur de médiation ou pool accepte les connexions entrantes à partir d’un homologue de passerelle.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les Ports à l’écoute de serveur de médiation

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour Business Server 2015Topology Builder**.
    
2. Dans le Générateur de topologies, dans l’arborescence de la console, développez le nœud **pools de médiation** et sélectionnez le serveur de médiation précédemment créé.
    
3. Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic Skype pour Business Server TLS et 5067 pour le trafic TLS à partir des pairs (par exemple, des passerelles, PBX ou SBCs). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.
    
4. Spécifiez que la souhaité TLS ou TCP écoute plage de ports du serveur de médiation acceptera des connexions entrantes à partir des passerelles RTPC.
    
    > [!NOTE]
    > Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.
  

