---
title: Créer votre topologie du périmètre pour Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Résumé : Apprenez à créer, publier et exporter votre topologie de serveur de transport Edge dans Skype pour Business Server.'
ms.openlocfilehash: 32273f7e0cf14b4ed5be3956eb69ef66a3b06fee
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223816"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Créer votre topologie du périmètre pour Skype pour Business Server
 
**Résumé :** Découvrez comment créer, publier et exporter votre topologie de serveur de transport Edge dans Skype pour Business Server.
  
Le Générateur de topologie est l’outil, que vous devez utiliser pour créer votre topologie de serveur de transport Edge, comme il est utilisé pour les composants de topologie pour Skype pour Business Server. Avant de suivre les étapes ci-dessous, vous devez avoir configuré au moins un pool frontal ou un serveur Standard Edition server.
  
Cet article couvre les rubriques suivantes :
  
- Créer votre topologie de serveur de transport Edge
    
- Publication de votre topologie de serveur Edge
    
- Exportation de votre topologie de serveur Edge
    
  > [!NOTE]
  > Pour suivre les étapes ci-dessous, vous devrez vous connecter aux serveurs de domaine répertoriés ci-après en tant qu’utilisateur membre des groupes de domaines suivants : 
  
- RTCUniversalServerAdmins
    
- DomainAdmins
    
## <a name="build-your-edge-server-topology"></a>Créer votre topologie de serveur de transport Edge

La création de votre Skype pour la topologie de serveur de périphérie Business Server, qui se compose d’une des trois options est la première étape du déploiement :
  
- Un serveur Edge unique
    
- Un pool de serveurs Edge de l’équilibrage de charge DNS (un ou plusieurs serveurs)
    
- Un équilibrage de charge matérielle équilibrée pool de serveurs Edge (un ou plusieurs serveurs)
    
Si vous ne savez pas ce dont vous avez besoin, prenez un moment pour consulter la documentation de planification avant de commencer à suivre cette procédure. Dans le cas contraire, vous pouvez commencer.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Définition de la topologie pour un serveur Edge unique

1. Ouvrez une session sur votre Skype pour Business Server Standard Edition server ou un Skype pour Business Server un pool frontal.
    
2. Une fois, ouvrez **Skype pour le Générateur de topologie Business Server**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. **Pools de serveurs Edge**d’avec le bouton droit, puis cliquez sur **pool de serveurs Edge de nouveau**.
    
5. Vous allez cliquez sur **suivant** dans l’écran **définir un nouveau Edge pool** .
    
6. Dans l’écran **définir le nom de domaine complet du pool Edge** , tapez le nom de domaine complet (FQDN) interne du serveur Edge sur le point d’utiliser et sélectionnez **pool d’un seul ordinateur**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous souhaitiez utiliser la même adresse IP et le nom de domaine complet pour votre service d’accès SIP, votre Skype pour le service de conférence Web Business Server et votre A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
   Ils sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur Edge interne ou externe (vous devez pour cela n’oubliez pas de l’étape 10). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool de serveurs Edge à utiliser une adresse NAT (traduction) de réseau pour l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **d’Accès SIP** . Ensuite, vous devez entrer des numéros de port différent pour chaque service edge afin de les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas l’activez la case à cocher **utiliser un nom de domaine complet et l’adresse IP unique** , vous devez maintenant entrer les trois noms de domaine complets externes pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Ici, vous devez taper l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
11. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Dans ce cas, tapez votre adresse IPv4 ou IPv6 externe (selon la situation qui vous utilisez) dans la zone de texte **Accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez votre adresse IPv4 ou IPv6 externe pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
12. Si vous décidez d’utiliser NAT à l’étape 8, vous obtiendrez maintenant un écran avec une zone de texte **adresse IP publique** . Vous devez entrez l’adresse IPv4 ou IPv6 public que vous avez défini pour A / V Edge service, être traduits par NAT. Cliquez ensuite sur **Suivant**.
    
13. L’écran suivant des est **définir le tronçon suivant**. Dans la zone **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
14. Dans l’écran de **pools frontaux associés** , vous devez spécifier un ou plusieurs pools internes, y compris les pools frontaux et les serveurs Standard Edition Server à associer à ce serveur de périphérie. Choisissez les noms des pools internes à l’aide de ce serveur de périphérie pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à prendre en compte ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message s’affiche pour vous indiquer sur l’autre serveur Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
15. Cliquez sur **Terminer** dans l’écran suivant.
    
16. Maintenant, vous serez en mesure de publier cette technologie mis à jour et suivez les instructions de [Déploiement des serveurs de périphérie dans Skype pour Business Server](deploy-edge-servers.md) à déployer sur votre serveur Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Définition de la topologie pour un serveur DNS pool de serveurs Edge avec équilibrage de charge

1. Ouvrez une session sur votre Skype pour Business Server Standard Edition server ou un Skype pour Business Server serveur frontal.
    
2. Une fois, ouvrez **Skype pour le Générateur de topologie Business Server**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. **Pools de serveurs Edge**d’avec le bouton droit, puis cliquez sur **pool de serveurs Edge de nouveau**.
    
5. Vous allez cliquez sur **suivant** dans l’écran **définir un nouveau Edge pool** .
    
6. Dans l’écran **définir le nom de domaine complet du pool Edge** , tapez le nom de domaine complet (FQDN) interne du pool Edge sur le point d’utiliser et sélectionnez **pool de plusieurs ordinateurs**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
    - Vous souhaitiez utiliser la même adresse IP et le nom de domaine complet pour votre service d’accès SIP, votre Skype pour le Service de conférence Web Business Server et votre A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
    - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
    - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Ils sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur Edge interne ou externe (vous devez pour cela n’oubliez pas de l’étape 11). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool de serveurs Edge à utiliser une adresse NAT (traduction) de réseau pour l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **d’Accès SIP** . Ensuite, vous devez entrer des numéros de port différent pour chaque service edge afin de les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas l’activez la case à cocher **utiliser un nom de domaine complet et l’adresse IP unique** , vous devez maintenant entrer les trois noms de domaine complets externes pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Maintenant, vous avez atteint l’écran **définir les ordinateurs de ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Ici, vous devez taper l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Dans ce cas, tapez votre adresse IPv4 ou IPv6 externe (selon la situation qui vous utilisez) dans la zone de texte **Accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez votre adresse IPv4 ou IPv6 externe pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur de périphérie que vous venez de créer doit maintenant figurer dans la boîte de dialogue **définir les ordinateurs de ce pool** .
    
14. Sur l’écran **définir les ordinateurs de ce pool** , cliquez à nouveau sur le bouton **Ajouter** et répétez les étapes 11 à 13 jusqu'à ce que vous avez ajouté tous les serveurs Edge que vous projetez d’avoir de ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. Si vous décidez d’utiliser NAT à l’étape 8, vous obtiendrez maintenant un écran avec une zone de texte **adresse IP publique** . Vous devez entrez l’adresse IPv4 ou IPv6 public que vous avez défini pour A / V Edge service, être traduits par NAT. Cliquez ensuite sur **Suivant**.
    
16. L’écran suivant des est **définir le tronçon suivant**. Dans la zone **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
17. Dans l’écran de **pools frontaux associés** , vous devez spécifier un ou plusieurs pools internes, y compris les pools frontaux et Standard Edition, à associer à ce serveur de périphérie. Choisissez les noms des pools internes à l’aide de ce serveur de périphérie pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à prendre en compte ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message s’affiche pour vous indiquer sur l’autre serveur Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
18. Cliquez sur **Terminer** dans l’écran suivant.
    
19. Maintenant, vous serez en mesure de publier cette technologie mis à jour et suivez les instructions de [Déploiement des serveurs de périphérie dans Skype pour Business Server](deploy-edge-servers.md) à déployer sur votre serveur Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Définition de la topologie pour un équilibrage de charge matérielle équilibrée pool de serveurs Edge

1. Ouvrez une session sur votre Skype pour Business Server Standard Edition server ou un Skype pour Business Server serveur frontal.
    
2. Une fois, ouvrez **Skype pour le Générateur de topologie Business Server**.
    
3. Dans l’arborescence de la console, développez le site que vous allez déployer le serveur Edge.
    
4. **Pools de serveurs Edge**d’avec le bouton droit, puis cliquez sur **pool de serveurs Edge de nouveau**.
    
5. Vous allez cliquez sur **suivant** dans l’écran **définir un nouveau Edge pool** .
    
6. Dans l’écran **définir le nom de domaine complet du pool Edge** , tapez le nom de domaine complet (FQDN) interne du pool Edge sur le point d’utiliser et sélectionnez **pool de plusieurs ordinateurs**, puis cliquez sur **suivant** lorsque vous avez terminé.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous souhaitiez utiliser la même adresse IP et le nom de domaine complet pour votre service d’accès SIP, votre Skype pour le Service de conférence Web Business Server et votre A / V Edge service. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Ils sont suffisamment explicites, si vous utilisez des adresses IPv4 ou IPv6, et que vous appliquez ces adresses sur votre serveur Edge interne ou externe (vous devez pour cela n’oubliez pas de l’étape 11).
    
     > [!NOTE]
     > Contrairement à l’autres deux options de topologie, lors de l’utilisation d’un mécanisme d’équilibrage de charge, vous **Ne doit pas** sélectionner l’option **l’adresse IP externe du Pool Edge est traduit par NAT**. Il s’agit **pas pris en charge**.
  
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez coché la case à cocher **utiliser l’adresse IP et un nom de domaine complet unique** , vous devez entrer votre nom de domaine complet externe unique dans la zone **d’Accès SIP** . Ensuite, vous devez entrer des numéros de port différent pour chaque service edge afin de les autoriser à se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas l’activez la case à cocher **utiliser un nom de domaine complet et l’adresse IP unique** , vous devez maintenant entrer les trois noms de domaine complets externes pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge. Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Maintenant, vous avez atteint l’écran **définir les ordinateurs de ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Ici, vous devez taper l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **l’adresse IPv6 interne** , en fonction des choix effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Dans ce cas, tapez votre adresse IPv4 ou IPv6 externe (selon la situation qui vous utilisez) dans la zone de texte **Accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez votre adresse IPv4 ou IPv6 externe pour le service Edge **d’Accès SIP** , le service Edge de **Conférence Web** et la **A / V** service Edge, puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur de périphérie que vous venez de créer doit maintenant figurer dans la boîte de dialogue **définir les ordinateurs de ce pool** .
    
14. Sur l’écran **définir les ordinateurs de ce pool** , cliquez à nouveau sur le bouton **Ajouter** et répétez les étapes 11 à 13 jusqu'à ce que vous avez ajouté tous les serveurs Edge que vous projetez d’avoir de ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. L’écran suivant des est **définir le tronçon suivant**. Dans la zone **pool du tronçon suivant** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez choisir le directeur. Then click **Next**.
    
16. Dans l’écran de **pools frontaux associés** , vous devez spécifier un ou plusieurs pools internes, y compris les pools frontaux et Standard Edition, à associer à ce serveur de périphérie. Choisissez les noms des pools internes à l’aide de ce serveur de périphérie pour communiquer avec des utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Quelque chose à prendre en compte ici est, si vos pools internes ou les serveurs autonomes utilisent déjà un autre Skype pour Business Server Edge Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome qui est dans ce cas, vous verrez un message s’affiche pour vous indiquer sur l’autre serveur Edge, et vous pouvez décider si vous souhaitez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
17. Cliquez sur **Terminer** dans l’écran suivant.
    
18. Maintenant, vous serez en mesure de publier cette technologie mis à jour et suivez les instructions de [Déploiement des serveurs de périphérie dans Skype pour Business Server](deploy-edge-servers.md) à déployer sur votre serveur Edge à partir d’ici.
    
## <a name="publish-your-edge-server-topology"></a>Publication de votre topologie de serveur Edge

Une fois que vous avez terminé les étapes ci-dessus, il est temps de publier cette nouvelle topologie, ce qui vous permettra également exporter vers votre Skype pour le pool d’entreprise serveur Edge ou Edge. Procédez comme suit :
  
1. Lancez le **générateur de topologie** (s’il n’a pas déjà été lancé au cours de la procédure précédente).
    
2. Dans **Le Générateur de topologie**, dans l’arborescence de la console, avec le bouton droit **Skype pour Business Server** , puis sur **Skype pour le Générateur de topologie Business Server**.
    
3. Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.
    
4. Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.
    
5. Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :
    
    - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
    - Pour fermer l’Assistant, cliquez sur **Terminer**.
    
## <a name="export-your-edge-server-topology"></a>Exportation de votre topologie de serveur Edge

Pour déployer avec succès, le Skype pour l’Assistant de déploiement Business Server doit avoir accès pour les données du magasin Central de gestion. Pour les serveurs internes de votre domaine ou de votre forêt, ceci est généralement simple. Serveurs de périphérie sont en dehors du domaine, et il est donc nécessaire exporter manuellement le fichier de topologie à l’emplacement du serveur de transport Edge, généralement sur un support physique. Cette exportation s’effectue via PowerShell :
  
1. Démarrez le **Skype pour Business Server Management Shell**.
    
2. Dans la zone **Skype pour Business Server Management Shell**, exécutez la commande suivante :
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiez le fichier exporté sur un support externe (par exemple, un USB ou du partage réseau que vous pouvez atteindre à partir de l’emplacement du serveur Edge).
    

