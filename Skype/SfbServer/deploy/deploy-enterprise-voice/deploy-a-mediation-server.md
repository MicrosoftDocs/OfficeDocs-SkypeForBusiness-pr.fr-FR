---
title: Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Découvrez comment définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server.'
ms.openlocfilehash: 558c1324b488d36f69f760a2dc0484f22586d93c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229103"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server
 
**Résumé :** Apprenez à définir et de déployer un serveur de médiation dans le Générateur de topologie dans Skype pour Business Server.
  
Les charges de travail voix entreprise, conférence rendez-vous et applications Enterprise Voice avancées (application Response Group, application parcage d’appel, le contrôle d’admission des appels (CAC) et ainsi de suite), sont disponibles dans les pools frontaux. La fonctionnalité du serveur de médiation est intégrée dans le serveur frontal. Un serveur de médiation autonome distinct n’est pas nécessaire. 
  
La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour vous connecter à votre infrastructure Enterprise Voice à votre fournisseur de jonction SIP, un serveur de médiation distinct doit être déployé.
  
La connexion entre Skype pour Business Server (soit un serveur de médiation colocalisé sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée une jonction. Les rubriques de cette section décrivent comment définir une jonction et comment déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Définition d’un serveur de médiation dans le générateur de topologie

Vous pouvez ajouter un serveur de médiation en tant qu’un rôle colocalisé sur un pool frontal ou définir un pool de serveurs de médiation autonome.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation à un pool frontal

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.
    
3. Dans l’arborescence de la console, cliquez sur le type de pool frontal que vous souhaitez, puis cliquez sur **Nouveau Front End pool..**.
    
4. Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.
    
5. **Rôles serveur colocalisés Select**, activez l’option **Colocaliser le serveur de médiation**.
    
    > [!NOTE]
    > Si le type de pool frontal que vous avez sélectionné est la version Enterprise Edition, le composant serveur de médiation s’être installé sur tous les serveurs frontaux de ce pool frontal. 
  
    > [!NOTE]
    > Le **pool du tronçon suivant** utilisé par le serveur de médiation sera le pool frontal lequel le serveur de médiation est colocalisé.
  
    > [!NOTE]
    > Le **pool de serveurs Edge** utilisé par le serveur de médiation sera le même pool Edge associé au pool frontal lequel le serveur de médiation est colocalisé.
  
6. Cliquez sur **Utiliser par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le réseau RTC.
    
7. Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.
    
    > [!NOTE]
    > Avant de passer à la prochaine étape du processus de déploiement de voix entreprise, assurez-vous que le pool de serveur de médiation (c'est-à-dire Front-End pool avec le composant serveur de médiation colocalisé) à l’aide de noms de domaines complets que vous avez spécifié. 
  
8. Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Pour ajouter un serveur de médiation autonome

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.
    
3. Dans l’arborescence de la console, cliquez sur le nœud **pools de médiation** , puis cliquez sur **pool de serveur de médiation**.
    
4. **Définir un nouveau Pool de médiation**, tapez le nom de domaine complet (FQDN) du pool serveur de médiation.
    
5. Effectuez ensuite l’une des opérations suivantes :
    
   - Si vous souhaitez déployer plusieurs serveurs de médiation du pool pour fournir une haute disponibilité, puis sélectionnez le **pool de plusieurs ordinateurs**.
    
     > [!NOTE]
     > Vous devez [déployer](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveurs de médiation contient plusieurs serveurs de médiation.
  
   - Si vous souhaitez ne déployer qu’un seul serveur de médiation du pool, car vous n’avez pas besoin de haute disponibilité, puis sélectionnez le **pool d’un seul ordinateur**. Ignorez l’étape suivante.
    
6. Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.
    
7. Dans la page **Sélectionner le tronçon suivant** , cliquez sur **pool du tronçon suivant**, cliquez sur le nom de domaine complet du pool frontal qui utilisera ce pool de serveur de médiation, puis cliquez sur **suivant**.
    
8. Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
   - Si vous souhaitez fournir une connectivité PSTN aux utilisateurs externes activés pour Enterprise Voice, sous **Sélectionnez le Pool Edge utilisé par ce serveur de médiation**, cliquez sur le nom de domaine complet du pool Edge Server qui utilise ce pool de serveur de médiation pour fournir une connectivité PSTN à les utilisateurs externes, puis cliquez sur **suivant**.
    
   - Si vous n’envisagez pas permettre aux utilisateurs externes pour Enterprise Voice, ou si vous ne souhaitez pas fournir une connectivité PSTN aux utilisateurs lorsqu’ils sont en dehors du réseau interne, cliquez sur **suivant**.
    
9. Cliquez sur le nœud **Skype pour Business Server 2015** , puis cliquez sur **Publier la topologie**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Définir les Ports d’écoute de serveur de médiation

Suivez les étapes décrites dans cette rubrique pour utiliser le Générateur de topologie pour définir les ports d’écoute à un serveur de médiation ou un pool pour accepter les connexions entrantes à partir d’un homologue de passerelle.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les Ports d’écoute de serveur de médiation

1. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de 2015Topology Business Server**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nœud **pools de médiation** et cliquez sur le serveur de médiation créé précédemment.
    
3. Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS Skype pour Business Server et 5067 pour le trafic TLS de homologues (tels que les passerelles, PBX ou SBC). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.
    
4. Spécifiez que la souhaitée TLS ou TCP d’écoute plage de ports du serveur de médiation accepter les connexions entrantes à partir de passerelles PSTN.
    
    > [!NOTE]
    > Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.
  

