---
title: Déploiement d’un serveur de médiation dans le générateur de topologies dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé: Découvrez comment définir et déployer un serveur de médiation dans le générateur de topologies dans Skype entreprise Server.'
ms.openlocfilehash: 61b90bb874d96579d975a1672238a7427350a5dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284647"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Déploiement d’un serveur de médiation dans le générateur de topologies dans Skype entreprise Server
 
**Résumé:** Apprenez à définir et déployer un serveur de médiation dans le générateur de topologies de Skype entreprise Server.
  
La charge de travail voix entreprise, les conférences rendez-vous et les applications Advanced Enterprise voix (application de groupe de réponse, application de stationnement d’appel, contrôle d’admission des appels (CAC), etc.), sont disponibles dans des regroupements front-end. Les fonctionnalités du serveur de médiation sont intégrées au serveur frontal. Il n’est pas nécessaire de disposer d’un serveur de médiation autonome séparé. 
  
La seule exception est si vous configurez une jonction SIP (Session Initiation Protocol) pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour connecter l’infrastructure vocale de votre entreprise à votre fournisseur SIP Trunk, un serveur de médiation distinct doit être déployé.
  
La connexion entre Skype entreprise Server (un serveur de médiation localisé sur un pool frontal ou un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée Trunk. Les rubriques de cette section expliquent comment définir un élément Trunk et comment déployer un serveur de médiation autonome si vous vous connectez à un Trunk SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Définition d’un serveur de médiation dans le générateur de topologie

Vous pouvez ajouter un serveur de médiation en tant que rôle colocalisé sur une réserve frontale ou définir un pool de serveurs de médiation autonome distinct.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation à un pool frontal

1. Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.
    
2. Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un pool frontal.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de réserve frontale souhaité, puis cliquez sur **nouveau pool frontal..**.
    
4. Naviguez dans l’Assistant **Définition d’un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.
    
5. Dans **sélection de rôles de serveur**colocalisés, activez l’option **Collocate médiation Server**.
    
    > [!NOTE]
    > Si le type de réserve frontale que vous avez sélectionné est l’édition entreprise, le composant serveur de médiation sera installé sur tous les serveurs front-end de cette liste frontale. 
  
    > [!NOTE]
    > Le **pool de prochains tronçons** utilisé par le serveur de médiation sera le pool frontal sur lequel est colocalisé le serveur de médiation.
  
    > [!NOTE]
    > Le **pool Edge** utilisé par le serveur de médiation sera le même pool de périphérie associé au pool frontal sur lequel est localisé le serveur de médiation.
  
6. Cliquez sur **définir par défaut** pour utiliser ce pool frontal pour acheminer les appels vers le RTC.
    
7. Cliquez sur **Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.
    
    > [!NOTE]
    > Avant de passer à l’étape suivante du processus de déploiement de voix entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire le pool frontal doté du composant de serveur de médiation) utilise les noms de domaine complets que vous avez spécifiés. 
  
8. Cliquez avec le bouton droit sur le nœud **Skype entreprise Server 2015** , puis cliquez sur **publier la topologie**.
    
### <a name="to-add-a-standalone-mediation-server"></a>Pour ajouter un serveur de médiation autonome

1. Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.
    
2. Dans le générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous voulez définir un serveur de médiation.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud Pools de **médiation** , puis cliquez sur **pool de serveurs de médiation**.
    
4. Dans **définir un nouveau pool de médiation**, tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.
    
5. Effectuez ensuite l’une des opérations suivantes :
    
   - Si vous voulez déployer plusieurs serveurs de médiation dans le pool afin d’offrir une disponibilité élevée, sélectionnez **plusieurs pools d’ordinateurs**.
    
     > [!NOTE]
     > Vous devez [déployer](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) pour prendre en charge les pools de serveurs de médiation qui disposent de plusieurs serveurs de médiation.
  
   - Si vous voulez déployer un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **pool d’ordinateurs unique**. Ignorez l’étape suivante.
    
6. Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.
    
7. Dans la page **Sélectionner le tronçon suivant** , cliquez sur **réserve de sauts suivant**, sur le nom de domaine complet (FQDN) du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **suivant**.
    
8. Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
   - Si vous voulez fournir une connectivité RTC aux utilisateurs externes activés pour Enterprise Voice, sous **Sélectionner le pool de périphériques utilisés par ce serveur de médiation**, cliquez sur le nom de domaine complet (FQDN) du pool de serveur Edge qui utilisera ce pool de serveurs de médiation pour fournir une connectivité PSTN à utilisateurs externes, puis cliquez sur **suivant**.
    
   - Si vous envisagez de ne pas autoriser les utilisateurs externes pour les voix d’entreprise, ou si vous ne souhaitez pas fournir de connectivité RTC aux utilisateurs en dehors du réseau interne, cliquez sur **suivant**.
    
9. Cliquez avec le bouton droit sur le nœud **Skype entreprise Server 2015** , puis cliquez sur **publier la topologie**.
    
## <a name="define-the-mediation-server-listening-ports"></a>Définir les ports d’écoute du serveur de médiation

Suivez les étapes décrites dans cette rubrique pour utiliser le générateur de topologie pour définir les ports d’écoute d’un serveur de médiation ou d’un pool qui acceptera les connexions entrantes d’un homologue de passerelle.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les ports d’écoute du serveur de médiation

1. Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.
    
2. Dans le générateur de topologie, dans l’arborescence de la console, développez le nœud Pools de **médiation** , puis cliquez avec le bouton droit sur le serveur de médiation précédemment créé.
    
3. Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS de Skype entreprise Server et 5067 pour le trafic TLS d’homologues (par exemple, les passerelles, PBXes ou SBCs). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.
    
4. Spécifiez la plage de port d’écoute TCP ou TLS souhaitée le serveur de médiation acceptera les connexions entrantes des passerelles RTC.
    
    > [!NOTE]
    > Vous n’êtes pas obligé d’entrer une plage de ports TCP si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.
  

