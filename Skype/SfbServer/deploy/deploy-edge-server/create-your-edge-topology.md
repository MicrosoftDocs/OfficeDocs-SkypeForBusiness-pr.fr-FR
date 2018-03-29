---
title: Création de votre topologie Edge pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Résumé : Apprenez à créer, publier et exporter votre topologie de serveur de transport Edge dans Skype pour Business Server 2015.'
ms.openlocfilehash: 336bef93fbb0d58c07ebd845fff2751e85464900
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-your-edge-topology-for-skype-for-business-server-2015"></a>Création de votre topologie Edge pour Skype Entreprise Server 2015
 
**Résumé :** Apprenez à créer, publier et exporter votre topologie de serveur de transport Edge dans Skype pour Business Server 2015.
  
Générateur de topologies est l’outil que vous souhaitez utiliser pour créer votre topologie de serveur de transport Edge, comme il est utilisé pour les composants de la topologie pour Skype pour Business Server 2015. Avant de suivre les étapes ci-dessous, vous devez avoir défini au moins un pool frontal ou un serveur Standard Edition.
  
Cet article couvre les rubriques suivantes :
  
- Créer votre topologie de serveur de transport Edge
    
- Publication de votre topologie de serveur Edge
    
- Exportation de votre topologie de serveur Edge
    
  > [!NOTE]
  > Pour suivre les étapes ci-dessous, vous devrez vous connecter aux serveurs de domaine répertoriés ci-après en tant qu’utilisateur membre des groupes de domaines suivants : 
  
- RTCUniversalServerAdmins
    
- DomainAdmins
    
## <a name="build-your-edge-server-topology"></a>Créer votre topologie de serveur de transport Edge

La première étape du déploiement construit votre Skype pour la topologie de serveur de transport Edge Business Server 2015, qui se compose d’une des trois options :
  
- Un seul serveur Edge
    
- Un pool de bord de l’équilibrage de la charge DNS (un ou plusieurs serveurs)
    
- Un matériel équilibrage pool de bord (un ou plusieurs serveurs)
    
Si vous ne savez pas ce dont vous avez besoin, prenez un moment pour consulter la documentation de planification avant de commencer à suivre cette procédure. Dans le cas contraire, vous pouvez commencer.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Définition de la topologie pour un seul serveur Edge

1. Ouvrez une session sur votre Skype pour Business Server 2015 Standard Edition server ou un Skype pour un pool frontal Business Server 2015.
    
2. Une fois, ouvrez des **Skype pour le Générateur de topologies Business Server 2015**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. Cliquez droit sur les **pools de bord**, puis cliquez sur **nouvelle arête pool**.
    
5. Vous cliquerez sur **suivant** sur l’écran **définissent bord pool** .
    
6. Sur l’écran **définir le nom de domaine complet du pool bord** , tapez le nom de domaine complet (FQDN) interne qui va utiliser le serveur de transport Edge et sélectionnez **pool d’un seul ordinateur**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous ne souhaitiez pas utiliser la même adresse IP et nom de domaine complet de votre service d’accès de SIP, votre Skype pour le service de conférence Web de Business Server 2015 et vos A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
   Ceux-ci sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur de transport Edge en interne ou en externe (vous aurez besoin de garder cela à l’esprit pour l’étape 10). Vous avez également l’option de configuration de votre serveur Edge ou votre pool de bord à utiliser une adresse de traduction d’adresse réseau de l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **Accès de SIP** . Ensuite, vous devrez entrer les numéros de port différents pour chaque service de bord pour les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activez la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez désormais entrer les noms de domaine complets à trois externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Vous êtes maintenant sur l’écran **définir l’adresse IP interne** . Ici, vous allez taper l’adresse IP de votre serveur de transport Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
11. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon vous utilisez) dans la zone de texte de **SIP l’accès** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si c’est le cas, entrez les adresses IPv4 ou IPv6 externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
12. Si vous avez choisi d’utiliser NAT à l’étape 8, vous aurez désormais un écran avec une zone de texte **adresse IP publique** . Vous devez saisir l’adresse IPv4 ou IPv6 publique que vous avez défini pour l’un / V Edge service traduits par NAT. Cliquez ensuite sur **Suivant**.
    
13. Écran suivant vers le haut est de **définir le saut suivant**. Dans la zone de **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
14. Dans l’écran **regroupements d’associer un Front-End** , vous devez spécifier un ou plusieurs pools internes, y compris les pools de Front-End et les serveurs Standard Edition, à associer à ce serveur de transport Edge. Choisissez les noms des pools internes à l’aide de ce serveur de transport Edge pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à retenir ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server 2015 Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message d’avertissement s’affiche vous informant sur l’autre serveur de transport Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
15. Cliquez sur **Terminer** dans l’écran suivant.
    
16. Maintenant, vous serez en mesure de publier cette technologie de mise à jour et suivez les instructions de [Déploiement de serveurs Edge dans Skype pour Business Server 2015](deploy-edge-servers.md) à déployer sur votre serveur de transport Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Définition de la topologie d’un serveur DNS charge équilibrée pool de serveur de transport Edge

1. Ouvrez une session sur votre Skype pour Business Server 2015 Standard Edition server ou un Skype pour Business Server 2015 serveur frontal.
    
2. Une fois, ouvrez des **Skype pour le Générateur de topologies Business Server 2015**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. Cliquez droit sur les **pools de bord**, puis cliquez sur **nouvelle arête pool**.
    
5. Vous cliquerez sur **suivant** sur l’écran **définissent bord pool** .
    
6. Sur l’écran **définir le nom de domaine complet du pool bord** , tapez le nom de domaine complet (FQDN) interne qui va utiliser le pool de bord et sélectionnez **plusieurs pool d’ordinateur**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
    - Vous ne souhaitiez pas utiliser la même adresse IP et nom de domaine complet de votre service d’accès de SIP, votre Skype pour le Service de conférence Web Business Server 2015 et vos A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
    - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
    - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
    Ceux-ci sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur de transport Edge en interne ou en externe (vous aurez besoin de garder cela à l’esprit de l’étape 11). Vous avez également l’option de configuration de votre serveur Edge ou votre pool de bord à utiliser une adresse de traduction d’adresse réseau de l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **Accès de SIP** . Ensuite, vous devrez entrer les numéros de port différents pour chaque service de bord pour les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activez la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez désormais entrer les noms de domaine complets à trois externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Maintenant, vous avez atteint l’écran **définir les ordinateurs dans ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant sur l’écran **définir l’adresse IP interne** . Ici, vous allez taper l’adresse IP de votre serveur de transport Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon vous utilisez) dans la zone de texte de **SIP l’accès** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si c’est le cas, entrez les adresses IPv4 ou IPv6 externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous venez de créer doit maintenant être affiché dans la boîte de dialogue **définir les ordinateurs dans ce pool** .
    
14. Sur l’écran **définir les ordinateurs dans ce pool** , cliquez de nouveau sur le bouton **Ajouter** et répétez les étapes 11 à 13 jusqu'à ce que vous avez ajouté tous les serveurs de bord que vous projetez d’avoir dans ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. Si vous avez choisi d’utiliser NAT à l’étape 8, vous aurez désormais un écran avec une zone de texte **adresse IP publique** . Vous devez saisir l’adresse IPv4 ou IPv6 publique que vous avez défini pour l’un / V Edge service traduits par NAT. Cliquez ensuite sur **Suivant**.
    
16. Écran suivant vers le haut est de **définir le saut suivant**. Dans la zone de **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
17. Dans l’écran **regroupements d’associer un Front-End** , vous devez spécifier un ou plusieurs pools internes, y compris les pools de Front-End et les pools de Standard Edition, à associer à ce serveur de transport Edge. Choisissez les noms des pools internes à l’aide de ce serveur de transport Edge pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à retenir ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server 2015 Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message d’avertissement s’affiche vous informant sur l’autre serveur de transport Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
18. Cliquez sur **Terminer** dans l’écran suivant.
    
19. Maintenant, vous serez en mesure de publier cette technologie de mise à jour et suivez les instructions de [Déploiement de serveurs Edge dans Skype pour Business Server 2015](deploy-edge-servers.md) à déployer sur votre serveur de transport Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Définition de la topologie d’une charge de matériel équilibrée pool de serveur de transport Edge

1. Ouvrez une session sur votre Skype pour Business Server 2015 Standard Edition server ou un Skype pour Business Server 2015 serveur frontal.
    
2. Une fois, ouvrez des **Skype pour le Générateur de topologies Business Server 2015**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. Cliquez droit sur les **pools de bord**, puis cliquez sur **nouvelle arête pool**.
    
5. Vous cliquerez sur **suivant** sur l’écran **définissent bord pool** .
    
6. Sur l’écran **définir le nom de domaine complet du pool bord** , tapez le nom de domaine complet (FQDN) interne qui va utiliser le pool de bord et sélectionnez **plusieurs pool d’ordinateur**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous ne souhaitiez pas utiliser la même adresse IP et nom de domaine complet de votre service d’accès de SIP, votre Skype pour le Service de conférence Web Business Server 2015 et vos A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
    Ceux-ci sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur de transport Edge en interne ou en externe (vous aurez besoin de garder cela à l’esprit de l’étape 11).
    
    > [!NOTE]
    > Contrairement à l’autres deux options de topologie, lors de l’utilisation d’un équilibreur de charge matériel, vous **Ne doit pas** sélectionnez l’option de **l’adresse IP externe du bord Pool est convertie par NAT**. C’est **pas pris en charge**.
  
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **Accès de SIP** . Ensuite, vous devrez entrer les numéros de port différents pour chaque service de bord pour les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activez la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez désormais entrer les noms de domaine complets à trois externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Maintenant, vous avez atteint l’écran **définir les ordinateurs dans ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant sur l’écran **définir l’adresse IP interne** . Ici, vous allez taper l’adresse IP de votre serveur de transport Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon vous utilisez) dans la zone de texte de **SIP l’accès** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si c’est le cas, entrez les adresses IPv4 ou IPv6 externes pour le service de bord **Accès de SIP** , le service Edge de **Conférence Web** et la **A / V** bord du service, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous venez de créer doit maintenant être affiché dans la boîte de dialogue **définir les ordinateurs dans ce pool** .
    
14. Sur l’écran **définir les ordinateurs dans ce pool** , cliquez de nouveau sur le bouton **Ajouter** et répétez les étapes 11 à 13 jusqu'à ce que vous avez ajouté tous les serveurs de bord que vous projetez d’avoir dans ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. Écran suivant vers le haut est de **définir le saut suivant**. Dans la zone de **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
16. Dans l’écran **regroupements d’associer un Front-End** , vous devez spécifier un ou plusieurs pools internes, y compris les pools de Front-End et les pools de Standard Edition, à associer à ce serveur de transport Edge. Choisissez les noms des pools internes à l’aide de ce serveur de transport Edge pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à retenir ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server 2015 Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message d’avertissement s’affiche vous informant sur l’autre serveur de transport Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
17. Cliquez sur **Terminer** dans l’écran suivant.
    
18. Maintenant, vous serez en mesure de publier cette technologie de mise à jour et suivez les instructions de [Déploiement de serveurs Edge dans Skype pour Business Server 2015](deploy-edge-servers.md) à déployer sur votre serveur de transport Edge à partir d’ici.
    
## <a name="publish-your-edge-server-topology"></a>Publication de votre topologie de serveur Edge

Une fois que vous avez terminé les étapes ci-dessus, il est temps de publier cette nouvelle topologie, ce qui vous permettra également exporter vers votre Skype pour le pool de serveur de transport Edge 2015 Business Server ou le bord. Procédez comme suit :
  
1. Lancez le **générateur de topologie** (s’il n’a pas déjà été lancé au cours de la procédure précédente).
    
2. Dans **Le Générateur de topologies**, dans l’arborescence de la console, cliquez sur **Skype pour Business Server 2015** , puis sur **Skype pour le Générateur de topologies serveur Business**.
    
3. Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.
    
4. Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.
    
5. Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :
    
    - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
    - Pour fermer l’Assistant, cliquez sur **Terminer**.
    
## <a name="export-your-edge-server-topology"></a>Exportation de votre topologie de serveur Edge

Pour déployer avec succès, le Skype pour l’Assistant de déploiement 2015 Business Server nécessite un accès pour les données du magasin Central de gestion. Pour les serveurs internes de votre domaine ou de votre forêt, ceci est généralement simple. Les serveurs Edge sont en dehors du domaine, et il est donc nécessaire de l’exporter manuellement le fichier de topologie à l’emplacement de serveur de transport Edge, généralement sur un média physique. Cette exportation s’effectue via PowerShell :
  
1. Démarrer le **Skype pour Business Server Management Shell**.
    
2. Dans la zone **Skype pour Business Server Management Shell**, exécutez la commande suivante :
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiez le fichier exporté vers un support externe (par exemple, un USB ou du partage réseau que vous pouvez atteindre à partir de l’emplacement du serveur de l’arête).
    

