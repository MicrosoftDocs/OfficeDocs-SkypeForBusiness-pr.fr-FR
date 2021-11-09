---
title: Créer votre topologie Edge pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Résumé : Découvrez comment créer, publier et exporter votre topologie de serveur Edge dans Skype Entreprise Server.'
ms.openlocfilehash: b016475f32e38b1353f7ef14f91e203843cd748b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844857"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Créer votre topologie Edge pour Skype Entreprise Server
 
**Résumé :** Découvrez comment créer, publier et exporter votre topologie de serveur Edge dans Skype Entreprise Server.
  
Le Générateur de topologie est l’outil que vous devez utiliser pour créer votre topologie de serveur Edge, tout comme il est utilisé pour n’importe quel composant de topologie pour Skype Entreprise Server. Avant de suivre les étapes ci-dessous, vous devez avoir installé au moins un pool frontal ou un Édition Standard serveur.
  
Nous couvrent les rubriques suivantes de cet article :
  
- Créer votre topologie de serveur Edge
    
- Publier votre topologie de serveur Edge
    
- Exporter votre topologie de serveur Edge
    
  > [!NOTE]
  > Pour suivre les étapes ci-dessous, vous devrez vous connecter aux serveurs de domaine mentionnés ci-dessous en tant qu’utilisateur membre des groupes de domaines suivants : 
  
- RTCUniversalServerAdmins
    
- Administrateurs du domaine
    
## <a name="build-your-edge-server-topology"></a>Créer votre topologie de serveur Edge

La première étape de déploiement consiste à créer Skype Entreprise Server topologie de serveur Edge, qui se compose de l’une des trois options suivantes :
  
- Un serveur Edge unique
    
- Un pool de serveurs Edge avec charge DNS équilibrée (un ou plusieurs serveurs)
    
- Un pool edge avec charge matérielle équilibrée (un ou plusieurs serveurs)
    
Si vous n’êtes pas sûr de ce dont vous avez besoin, avant de commencer à suivre ces étapes, il est temps de passer en premier dans la documentation de planification. Sinon, commençons.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Définition de la topologie pour un serveur Edge unique

1. Connectez-vous à Skype Entreprise Server Édition Standard serveur ou à un pool Skype Entreprise Server frontal.
    
2. Une fois qu’il est **Skype Entreprise Server, ouvrez le Générateur de topologie.**
    
3. Dans l’arborescence de la console, développez le site où vous allez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit **sur les pools de** périphérie, puis cliquez sur Nouveau pool **edge.**
    
5. Vous allez cliquer sur **Suivant** dans l’écran **Définir un nouveau pool edge.**
    
6. Dans l’écran Définir le nom de domaine complet du pool de serveurs Edge, tapez le nom de domaine complet  (FQDN) interne que le serveur Edge va utiliser, puis sélectionnez Pool d’un seul **ordinateur,** en cliquant sur Suivant une fois terminé. 
    
7. Dans **l’écran Sélectionner des** fonctionnalités, vous avez le choix entre :
    
   - Vous avez peut-être l’intention d’utiliser les mêmes FQDN et adresse IP pour votre service d’accès SIP, votre service de conférence web Skype Entreprise Server et votre service Edge A/V. Si c’est le cas, vous devez choisir la case à cocher Utiliser un seul **FQDN** et une seule adresse IP (et gardez ceci à l’esprit pour l’étape 9 ci-dessous)
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061).**
    
8. Une fois que vous avez cliqué **sur Suivant,** vous vous trouverez sur l’écran **Options IP.** Vos options sont les suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
   Ces éléments sont assez explicites, que vous utilisiez des adresses IPv4 ou IPv6 et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez garder cela à l’esprit pour l’étape 10). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool de serveurs Edge pour utiliser une adresse NAT (Network Address Translation) pour l’adresse IP externe. Pour ce faire, cochez la case NAT pour sélectionner l’adresse IP externe de ce **pool edge.** Cliquez **sur Suivant** lorsque vous êtes prêt.
    
9. Dans l’écran Des FQDN externes, vos choix dépendent de la sélection que vous avez faite à l’étape 7 ci-dessus.
    
   - Si vous avez coché la case Utiliser un seul nom **deqdn** et une seule adresse IP, vous devez entrer votre nom de groupe externe unique dans la zone **d’accès SIP.** Ensuite, vous devez entrer différents numéros de port pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’accès **SIP,** 444 pour le service Edge de conférence **web** et 443 pour le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
   - Si vous n’avez pas cocher la case Utiliser un seul **FQDN** et une seule adresse IP, vous devez maintenant entrer les trois FQDN externes pour le service Edge d’accès **SIP,** le service Edge de conférence **Web** et le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
10. Vous êtes maintenant sur l’écran **Définir l’adresse IP** interne. Vous allez taper l’adresse IP de votre serveur Edge dans les zones de texte Adresse **IPv4** interne et **Adresse IPv6** interne, en fonction des choix que vous avez effectués à l’étape 8. Cliquez **sur Suivant** lorsque vous êtes prêt.
    
11. Dans **l’écran Définir l’adresse IP** externe, vous avez plusieurs options en fonction de vos choix précédents :
    
    - Vous utilisez peut-être un seul FQDN pour tous les services. Si c’est le cas, tapez votre adresse IPv4 ou IPv6 externe (quelle que soit l’adresse que vous utilisez) dans la zone de texte **Accès SIP,** puis cliquez sur **Suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de noms de service et adresses IP distincts pour les services. Si c’est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d’accès **SIP,** le service Edge de conférence **web** et le service Edge **A/V,** puis cliquez sur Suivant **.**
    
    > [!NOTE]
    > Si vous n’avez pas précédemment choisi d’activer et d’attribuer l’adressare IPv6, cette boîte de dialogue ne s’verra pas. C’est normal, il vous suffit d’aller à l’étape suivante. 
  
12. Si vous avez choisi d’utiliser nat à l’étape 8, vous obtenez maintenant un écran avec une boîte de texte **d’adresse IP** publique. Vous devez entrer l’adresse IPv4 publique et/ou IPv6 que vous avez définie pour le service Edge A/V, pour être traduite par NAT. Cliquez ensuite sur **Next (Suivant)**.
    
13. L’écran suivant est **Définir le saut suivant.** Dans la **zone Pool du saut** suivant, sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez le choisir. Cliquez ensuite sur **Next (Suivant)**.
    
14. Dans  l’écran Pools frontux associés, vous devez spécifier un ou plusieurs pools internes, y compris les pools frontux et les serveurs Édition Standard, à associer à ce serveur Edge. Choisissez simplement les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Gardez à l’esprit que si vos pools internes ou serveurs autonomes utilisent déjà un serveur Edge Skype Entreprise Server différent, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un avertissement s’affiche vous avertissant de l’autre serveur Edge et vous pouvez décider si vous souhaitez continuer ou non. Si vous allez de l’avant avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
15. Cliquez **sur Terminer** sur l’écran suivant.
    
16. Vous pourrez maintenant publier cette technologie mise à jour et suivre les instructions dans Déployer des serveurs Edge dans [Skype Entreprise Server](deploy-edge-servers.md) pour le déployer sur votre serveur Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Définition de la topologie pour un pool de serveurs Edge avec charge DNS équilibrée

1. Connectez-vous à Skype Entreprise Server Édition Standard serveur ou à un Skype Entreprise Server frontal.
    
2. Une fois qu’il est **Skype Entreprise Server, ouvrez le Générateur de topologie.**
    
3. Dans l’arborescence de la console, développez le site où vous allez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit **sur les pools de** périphérie, puis cliquez sur Nouveau pool **edge.**
    
5. Vous allez cliquer sur **Suivant** dans l’écran **Définir un nouveau pool edge.**
    
6. Dans l’écran Définir le nom de domaine complet du **pool** de périphérie, tapez le nom de domaine complet interne  que le pool de périphérie va utiliser, puis sélectionnez Pool de plusieurs ordinateurs, en cliquant sur Suivant une fois terminé.
    
7. Dans **l’écran Sélectionner des** fonctionnalités, vous avez le choix entre :
    
    - Vous avez peut-être l’intention d’utiliser les mêmes FQDN et adresse IP pour votre service d’accès SIP, votre service de conférence web Skype Entreprise Server et votre service Edge A/V. Si c’est le cas, vous devez choisir la case à cocher Utiliser un seul **FQDN** et une seule adresse IP (et gardez ceci à l’esprit pour l’étape 9 ci-dessous)
    
    - Si vous envisagez d’activer la fédération, activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061).**
    
8. Une fois que vous avez cliqué **sur Suivant,** vous vous trouverez sur l’écran **Options IP.** Vos options sont les suivantes :
    
    - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Elles sont assez explicites, que vous utilisiez des adresses IPv4 ou IPv6 et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez garder cela à l’esprit pour l’étape 11). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool de serveurs Edge pour utiliser une adresse NAT (Network Address Translation) pour l’adresse IP externe. Pour ce faire, cochez la case NAT pour sélectionner l’adresse IP externe de ce **pool edge.** Cliquez **sur Suivant** lorsque vous êtes prêt.
    
9. Dans l’écran Des FQDN externes, vos choix dépendent de la sélection que vous avez faite à l’étape 7 ci-dessus.
    
   - Si vous avez coché la case Utiliser un seul nom **deqdn** et une seule adresse IP, vous devez entrer votre nom de groupe externe unique dans la zone **d’accès SIP.** Ensuite, vous devez entrer différents numéros de port pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’accès **SIP,** 444 pour le service Edge de conférence **web** et 443 pour le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
   - Si vous n’avez pas cocher la case Utiliser un seul **FQDN** et une seule adresse IP, vous devez maintenant entrer les trois FQDN externes pour le service Edge d’accès **SIP,** le service Edge de conférence **Web** et le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
10. Vous avez maintenant atteint **l’écran Définir les ordinateurs de cet écran de pool.** Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant sur l’écran **Définir l’adresse IP** interne. Vous allez taper l’adresse IP de votre serveur Edge dans les zones de texte Adresse **IPv4** interne et **Adresse IPv6** interne, en fonction des choix que vous avez effectués à l’étape 8. Cliquez **sur Suivant** lorsque vous êtes prêt.
    
12. Dans **l’écran Définir l’adresse IP** externe, vous avez plusieurs options en fonction de vos choix précédents :
    
    - Vous utilisez peut-être un seul FQDN pour tous les services. Si c’est le cas, tapez votre adresse IPv4 ou IPv6 externe (quelle que soit l’adresse que vous utilisez) dans la zone de texte **Accès SIP,** puis cliquez sur **Suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de noms de service et adresses IP distincts pour les services. Si c’est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d’accès **SIP,** le service Edge de conférence **web** et le service Edge **A/V,** puis cliquez sur Suivant **.**
    
    > [!NOTE]
    > Si vous n’avez pas précédemment choisi d’activer et d’attribuer l’adressare IPv6, cette boîte de dialogue ne s’verra pas. C’est normal, il vous suffit d’aller à l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous avez créé doit maintenant être répertorié dans la boîte de dialogue Définir les ordinateurs **de ce pool.**
    
14. Dans l’écran Définir les ordinateurs de  ce **pool,** cliquez à nouveau sur le bouton Ajouter et répétez les étapes 11 à 13 jusqu’à ce que vous ajoutiez tous les serveurs Edge que vous souhaitez avoir dans ce pool. Lorsque cette étape est terminée, cliquez sur **Suivant.**
    
15. Si vous avez choisi d’utiliser nat à l’étape 8, vous obtenez maintenant un écran avec une boîte de texte **d’adresse IP** publique. Vous devez entrer l’adresse IPv4 publique et/ou IPv6 que vous avez définie pour le service Edge A/V, pour être traduite par NAT. Cliquez ensuite sur **Next (Suivant)**.
    
16. L’écran suivant est **Définir le saut suivant.** Dans la **zone Pool du saut** suivant, sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez le choisir. Cliquez ensuite sur **Next (Suivant)**.
    
17. Dans  l’écran Pools frontux associés, vous devez spécifier un ou plusieurs pools internes, y compris les pools frontux et les pools Édition Standard, à associer à ce serveur Edge. Choisissez simplement les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Gardez à l’esprit que si vos pools internes ou serveurs autonomes utilisent déjà un serveur Edge Skype Entreprise Server différent, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un avertissement s’affiche vous avertissant de l’autre serveur Edge et vous pouvez décider si vous souhaitez continuer ou non. Si vous allez de l’avant avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
18. Cliquez **sur Terminer** sur l’écran suivant.
    
19. Vous pourrez maintenant publier cette technologie mise à jour et suivre les instructions dans Déployer des serveurs Edge dans [Skype Entreprise Server](deploy-edge-servers.md) pour le déployer sur votre serveur Edge à partir d’ici.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Définition de la topologie pour un pool de serveurs Edge avec charge matérielle équilibrée

1. Connectez-vous à Skype Entreprise Server Édition Standard serveur ou à un Skype Entreprise Server frontal.
    
2. Une fois qu’il est **Skype Entreprise Server, ouvrez le Générateur de topologie.**
    
3. Dans l’arborescence de la console, développez le site où vous allez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit **sur les pools de** périphérie, puis cliquez sur Nouveau pool **edge.**
    
5. Vous allez cliquer sur **Suivant** dans l’écran **Définir un nouveau pool edge.**
    
6. Dans l’écran Définir le nom de domaine complet du pool de périphérie, tapez le nom de domaine complet (FQDN) interne que le pool edge va utiliser, puis sélectionnez Pool de plusieurs ordinateurs, en cliquant sur Suivant une fois terminé.   
    
7. Dans **l’écran Sélectionner des** fonctionnalités, vous avez le choix entre :
    
   - Vous avez peut-être l’intention d’utiliser les mêmes FQDN et adresse IP pour votre service d’accès SIP, votre service de conférence web Skype Entreprise Server et votre service Edge A/V. Si c’est le cas, vous devez choisir la case à cocher Utiliser un seul **FQDN** et une seule adresse IP (et gardez ceci à l’esprit pour l’étape 9 ci-dessous)
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher Activer la fédération pour ce **pool Edge (port 5061).**
    
8. Une fois que vous avez cliqué **sur Suivant,** vous vous trouverez sur l’écran **Options IP.** Vos options sont les suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Ces éléments sont assez explicites, que vous utilisiez des adresses IPv4 ou IPv6 et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez garder cela à l’esprit pour l’étape 11).
    
     > [!NOTE]
     > Contrairement aux deux autres options de topologie, lorsque  vous utilisez un équilibreur de charge matérielle, vous NE DEVEZ PAS sélectionner l’option L’adresse IP externe du **pool edge** est traduite par NAT . Cela **n’est pas pris en charge.**
  
9. Dans l’écran Des FQDN externes, vos choix dépendent de la sélection que vous avez faite à l’étape 7 ci-dessus.
    
   - Si vous avez coché la case Utiliser un seul nom **deqdn** et une seule adresse IP, vous devez entrer votre nom de groupe externe unique dans la zone **d’accès SIP.** Ensuite, vous devez entrer différents numéros de port pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’accès **SIP,** 444 pour le service Edge de conférence **web** et 443 pour le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
   - Si vous n’avez pas cocher la case Utiliser un seul **FQDN** et une seule adresse IP, vous devez maintenant entrer les trois FQDN externes pour le service Edge d’accès **SIP,** le service Edge de conférence **Web** et le service Edge **A/V.** Sélectionnez **Suivant** lorsque vous avez terminé.
    
10. Vous avez maintenant atteint **l’écran Définir les ordinateurs de cet écran de pool.** Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant sur l’écran **Définir l’adresse IP** interne. Vous allez taper l’adresse IP de votre serveur Edge dans les zones de texte Adresse **IPv4** interne et **Adresse IPv6** interne, en fonction des choix que vous avez effectués à l’étape 8. Cliquez **sur Suivant** lorsque vous êtes prêt.
    
12. Dans **l’écran Définir l’adresse IP** externe, vous avez plusieurs options en fonction de vos choix précédents :
    
    - Vous utilisez peut-être un seul FQDN pour tous les services. Si c’est le cas, tapez votre adresse IPv4 ou IPv6 externe (quelle que soit l’adresse que vous utilisez) dans la zone de texte **Accès SIP,** puis cliquez sur **Suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de noms de service et adresses IP distincts pour les services. Si c’est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d’accès **SIP,** le service Edge de conférence **web** et le service Edge **A/V,** puis cliquez sur Suivant **.**
    
    > [!NOTE]
    > Si vous n’avez pas précédemment choisi d’activer et d’attribuer l’adressare IPv6, cette boîte de dialogue ne s’verra pas. C’est normal, il vous suffit d’aller à l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous avez créé doit maintenant être répertorié dans la boîte de dialogue Définir les ordinateurs **de ce pool.**
    
14. Dans l’écran Définir les ordinateurs de  ce **pool,** cliquez à nouveau sur le bouton Ajouter et répétez les étapes 11 à 13 jusqu’à ce que vous ajoutiez tous les serveurs Edge que vous souhaitez avoir dans ce pool. Lorsque cette étape est terminée, cliquez sur **Suivant.**
    
15. L’écran suivant est **Définir le saut suivant.** Dans la **zone Pool du saut** suivant, sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un directeur dans votre environnement, vous devez le choisir. Cliquez ensuite sur **Next (Suivant)**.
    
16. Dans  l’écran Pools frontux associés, vous devez spécifier un ou plusieurs pools internes, y compris les pools frontux et les pools Édition Standard, à associer à ce serveur Edge. Choisissez simplement les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Gardez à l’esprit que si vos pools internes ou serveurs autonomes utilisent déjà un serveur Edge Skype Entreprise Server différent, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un avertissement s’affiche vous avertissant de l’autre serveur Edge et vous pouvez décider si vous souhaitez continuer ou non. Si vous allez de l’avant avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
17. Cliquez **sur Terminer** sur l’écran suivant.
    
18. Vous pourrez maintenant publier cette technologie mise à jour et suivre les instructions dans Déployer des serveurs Edge dans [Skype Entreprise Server](deploy-edge-servers.md) pour le déployer sur votre serveur Edge à partir d’ici.
    
## <a name="publish-your-edge-server-topology"></a>Publier votre topologie de serveur Edge

Une fois que vous avez terminé les étapes ci-dessus, il est temps de publier cette nouvelle topologie, qui vous permettra également de l’exporter vers votre serveur Edge Skype Entreprise Server ou votre pool de serveurs Edge. Procédez comme suit :
  
1. Démarrez **le Générateur de** topologie (s’il n’a pas déjà démarré à partir de la procédure précédente).
    
2. Dans **le Générateur de topologie,** dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype Entreprise Server** puis cliquez sur Skype Entreprise Server générateur **de topologie.**
    
3. Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.
    
4. Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.
    
5. Lorsque l’état indique que la création de la base de données a réussi, faites les choses suivantes :
    
    - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
    - Pour fermer l’Assistant, cliquez sur **Terminer**.
    
## <a name="export-your-edge-server-topology"></a>Exporter votre topologie de serveur Edge

Pour un déploiement réussi, l’Assistant Skype Entreprise Server déploiement doit accéder aux données du magasin central de gestion. Pour les serveurs internes de votre domaine ou forêt, cette procédure est généralement simple. Les serveurs Edge sont en dehors du domaine et il est donc nécessaire d’exporter manuellement le fichier de topologie vers l’emplacement du serveur Edge, généralement sur un support physique. Cette exportation est effectuée via PowerShell :
  
1. Démarrez le **Skype Entreprise Server Management Shell.**
    
2. Dans **l’Skype Entreprise Server Management Shell,** exécutez les commandes suivantes :
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiez le fichier exporté sur un support externe (par exemple, un lecteur USB ou un partage réseau que vous pouvez atteindre à partir de l’emplacement du serveur Edge).
    

