---
title: Déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
description: 'Résumé : Découvrez comment définir et déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise Server.'
ms.openlocfilehash: 7dd3704b47b384d3fab62a7cc051adcf5b380c0e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857031"
---
# <a name="deploy-a-mediation-server-in-topology-builder-in-skype-for-business-server"></a>Déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise Server
 
**Résumé :** Découvrez comment définir et déployer un serveur de médiation dans le Générateur de topologies dans Skype Entreprise Server.
  
La charge de travail Voix Entreprise, les conférences téléphoniques et les applications Voix Entreprise avancées (application Response Group, application de parcage d’appel, contrôle d’admission des appels, etc.) sont disponibles dans les pools frontux. La fonctionnalité du serveur de médiation est intégrée au serveur frontal. Un serveur de médiation autonome distinct n’est pas nécessaire. 
  
La seule exception est si vous configurez une jonction SIP pour la connexion à un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet. Pour connecter votre infrastructure Voix Entreprise réseau à votre fournisseur de trunks SIP, un serveur de médiation distinct doit être déployé.
  
La connexion entre Skype Entreprise Server (soit un serveur de médiation cocté sur un pool frontal, soit un serveur de médiation autonome) et une passerelle est définie comme une association logique appelée une connexion. Les rubriques de cette section décrivent comment définir une jonction et déployer un serveur de médiation autonome, si vous vous connectez à une jonction SIP.
  
## <a name="define-a-mediation-server-in-topology-builder"></a>Définition d’un serveur de médiation dans le générateur de topologie

Vous pouvez ajouter un serveur de médiation en tant que rôle c colloc sur un pool frontal ou définir un pool de serveurs de médiation autonome distinct.
  
### <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Pour ajouter un serveur de médiation à un pool frontal

1. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un pool frontal.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur le type de pool frontal voulu, puis cliquez sur **Nouveau pool frontal.**
    
4. Naviguez au sein de l’Assistant permettant de **Définir un nouveau pool frontal** jusqu’à ce que vous accédiez à la page **Sélectionner des rôles serveur colocalisés**.
    
5. Dans **Sélectionner des rôles serveur cochez** l’option **Cochez le serveur de médiation.**
    
    > [!NOTE]
    > Si le type de pool frontal que vous avez sélectionné est le Êdition Entreprise, le composant serveur de médiation sera installé sur tous les serveurs frontux de ce pool frontal. 
  
    > [!NOTE]
    > Le **pool du saut suivant** utilisé par le serveur de médiation sera le pool frontal sur lequel le serveur de médiation est coqueté.
  
    > [!NOTE]
    > Le **pool de serveurs** Edge utilisé par le serveur de médiation sera le même pool de serveurs Edge associé au pool frontal sur lequel le serveur de médiation est coqueté.
  
6. Cliquez **sur Utiliser par** défaut pour utiliser ce pool frontal pour router les appels vers le PSTN.
    
7. Cliquez **sur Terminer** lorsque vous avez terminé d’associer un ou plusieurs homologues au pool frontal.
    
    > [!NOTE]
    > Avant de passer à l’étape suivante du processus de déploiement d’Voix Entreprise, assurez-vous que le pool de serveurs de médiation (c’est-à-dire, le pool frontal avec le composant serveur de médiation cocéré) utilise les FQDN que vous avez spécifiés. 
  
8. Cliquez avec le bouton **droit Skype Entreprise Server nœud 2015,** puis cliquez sur **Publier la topologie.**
    
### <a name="to-add-a-standalone-mediation-server"></a>Pour ajouter un serveur de médiation autonome

1. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nom du site pour lequel vous souhaitez définir un serveur de médiation.
    
3. Dans l’arborescence de la console, cliquez avec le bouton droit sur le nœud **pools** de médiation, puis cliquez sur **Pool de serveurs de médiation.**
    
4. Dans **Définir un nouveau pool de médiation,** tapez le nom de domaine complet (FQDN) du pool de serveurs de médiation.
    
5. Effectuez ensuite l’une des opérations suivantes :
    
   - Si vous souhaitez déployer plusieurs serveurs de médiation dans le pool pour fournir une haute disponibilité, sélectionnez **Pool de plusieurs ordinateurs.**
    
     > [!NOTE]
     > Vous devez déployer [pour prendre](../../plan-your-deployment/network-requirements/load-balancing.md#BKMK_DNSLoadBalancing) en charge les pools de serveurs de médiation qui ont plusieurs serveurs de médiation.
  
   - Si vous souhaitez déployer un seul serveur de médiation dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez **Pool d’un seul ordinateur.** Ignorez l’étape suivante.
    
6. Si vous avez sélectionné **Pool de plusieurs ordinateurs** à l’étape précédente, dans l’élément **Définissez les ordinateurs inclus dans ce pool**, cliquez sur **Nom de domaine complet de l’ordinateur**, tapez le nom de domaine complet de chaque serveur présent dans le pool, puis cliquez sur **Ajouter**. Répétez cette étape pour tous les autres serveurs de médiation que vous souhaitez ajouter au pool. Une fois que vous avez défini tous les ordinateurs du pool, cliquez sur **Suivant**.
    
7. Dans **la** page Sélectionner le saut suivant, cliquez sur Pool du saut **suivant,** cliquez sur le nom de groupe du pool frontal qui utilisera ce pool de serveurs de médiation, puis cliquez sur **Suivant**.
    
8. Dans la page **Sélectionner un serveur Edge**, effectuez l’une des opérations suivantes :
    
   - Si vous souhaitez fournir une connectivité PSTN à des utilisateurs externes activés pour Voix Entreprise, sous Sélectionner un **pool de** serveurs Edge utilisé par ce serveur de médiation, cliquez sur le nom de groupe du pool de serveurs Edge qui utilisera ce pool de serveurs de médiation pour fournir une connectivité PSTN à ces utilisateurs externes, puis cliquez sur **Suivant**.
    
   - Si vous ne prévoyez pas d’activer les utilisateurs externes pour Voix Entreprise, ou si vous ne souhaitez pas fournir de connectivité PSTN aux utilisateurs lorsqu’ils sont en dehors du réseau interne, cliquez sur **Suivant**.
    
9. Cliquez avec le bouton **droit Skype Entreprise Server nœud 2015,** puis cliquez sur **Publier la topologie.**
    
## <a name="define-the-mediation-server-listening-ports"></a>Définir les ports d’écoute du serveur de médiation

Suivez les étapes de cette rubrique pour utiliser le Générateur de topologie afin de définir les ports d’écoute qu’un serveur de médiation ou un pool acceptera les connexions entrantes d’un homologue de passerelle.
  
### <a name="to-modify-the-mediation-server-listening-ports"></a>Pour modifier les ports d’écoute du serveur de médiation

1. Démarrez le Générateur de topologie : cliquez sur Démarrer, sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Skype Entreprise Server **2015Topology Builder**.
    
2. Dans le Générateur de topologie, dans l’arborescence de la console, développez le nœud **pools** de médiation et cliquez avec le bouton droit sur le serveur de médiation précédemment créé.
    
3. Par défaut, les ports d’écoute SIP sur le serveur de médiation sont 5070 pour le trafic TLS à partir de Skype Entreprise Server et 5067 pour le trafic TLS provenant d’homologues (par exemple, passerelles, PBXes ou SCS). Le port TCP est désactivé par défaut. Vous devez activer le port TCP si vous disposez de passerelles qui ne prennent pas en charge le protocole TLS.
    
4. Spécifiez la plage de ports d’écoute TLS ou TCP souhaitée que le serveur de médiation acceptera les connexions entrantes à partir des passerelles PSTN.
    
    > [!NOTE]
    > L’entrée d’une plage de ports TCP n’est pas nécessaire, si l’option **Activer le port TCP** n’est pas activée. Ce paramètre est facultatif.
  

