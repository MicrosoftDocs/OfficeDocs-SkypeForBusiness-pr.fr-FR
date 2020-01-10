---
title: Créer votre topologie Edge pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Résumé : Découvrez comment créer, publier et exporter votre topologie de serveur Edge dans Skype entreprise Server.'
ms.openlocfilehash: c625656f1686b6e72be2f0223d6560464bb9e7bc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001474"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Créer votre topologie Edge pour Skype entreprise Server
 
**Résumé :** Découvrez comment créer, publier et exporter votre topologie de serveur Edge dans Skype entreprise Server.
  
Le générateur de topologie est l’outil que vous devez utiliser pour créer votre topologie de serveur Edge, comme pour n’importe quel composant topologique pour Skype entreprise Server. Avant de suivre les étapes ci-dessous, vous devrez configurer au moins un pool frontal ou un serveur Standard Edition Server.
  
Cet article couvre les rubriques suivantes :
  
- Créer votre topologie de serveur Edge
    
- Publication de votre topologie de serveur Edge
    
- Exportation de votre topologie de serveur Edge
    
  > [!NOTE]
  > Pour suivre les étapes ci-dessous, vous devrez vous connecter aux serveurs de domaine répertoriés ci-après en tant qu’utilisateur membre des groupes de domaines suivants : 
  
- RTCUniversalServerAdmins
    
- DomainAdmins
    
## <a name="build-your-edge-server-topology"></a>Créer votre topologie de serveur Edge

La première étape de déploiement consiste à créer votre topologie de serveur Edge Skype entreprise Server, composée de l’une des trois options suivantes :
  
- Serveur Edge unique
    
- Un pool Edge équilibré de charge DNS (un ou plusieurs serveurs);
    
- Pool Edge équilibré de la charge matérielle (un ou plusieurs serveurs)
    
Si vous ne savez pas ce dont vous avez besoin, prenez un moment pour consulter la documentation de planification avant de commencer à suivre cette procédure. Dans le cas contraire, vous pouvez commencer.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Définition de la topologie pour un serveur Edge unique

1. Connectez-vous à votre serveur Skype entreprise Server Standard Edition Server ou un pool frontal Skype entreprise Server.
    
2. Ouvrez ensuite le **Générateur de topologie Skype entreprise Server**.
    
3. Dans l’arborescence de la console, développez le site sur lequel vous voulez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle réserve de périphérie**.
    
5. Cliquez sur **suivant** dans l’écran **définir un nouveau pool de bords** .
    
6. Dans l’écran **définir le nom de** domaine complet du pool de bords, tapez le nom de domaine complet (FQDN) interne que le serveur de périphérie va utiliser, puis sélectionnez **pool d’ordinateurs unique**et cliquez sur **suivant** lorsque vous avez fini.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous pouvez utiliser les mêmes nom de domaine complet et adresse IP pour votre service d’accès SIP, votre service de conférence Web Skype entreprise Server et votre service Edge A/V. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
   Ce type d’utilisation est évident, que vous utilisiez une adresse IPv4 ou IPv6, et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez veiller à ce que vous deviez le garder à l’esprit pour l’étape 10). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool Edge pour utiliser une adresse de traduction d’adresses réseau (NAT) pour l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer votre nom de domaine complet unique dans la zone **accès SIP** . Ensuite, vous devez entrer des numéros de port différents pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer les trois noms de domaine complets (FQDN) externes pour le service **SIP Access** Edge, le service Edge de **conférence Web** et le service Edge **a/V** . Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Dans cet exemple, entrez l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **adresse IPv6 interne** , en fonction des choix que vous avez effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
11. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon ce que vous utilisez) dans la zone de texte **accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d' **accès SIP** , le service Edge de **conférence Web** et le service Edge **A/V** , puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
12. Si vous avez opté pour une utilisation de la traduction d’adresses à l’étape 8, vous obtenez désormais un écran contenant une zone de texte d' **adresse IP publique** . Vous devez entrer l’adresse IPv4 publique et/ou IPv6 que vous avez définie pour le service Edge A/V, qui sera traduite par tar. Cliquez ensuite sur **Suivant**.
    
13. L’écran suivant permet **de définir le saut suivant**. Dans la zone **réserve de prochains tronçons** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un réalisateur dans votre environnement, vous devez choisir le réalisateur. Then click **Next**.
    
14. Dans l’écran **Associate front end** , vous devez spécifier une ou plusieurs grappes internes, y compris des pools front end et des serveurs Standard Edition, à associer à ce serveur Edge. Il suffit de sélectionner les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Pour garder à l’esprit les points suivants : si vos pools internes ou serveurs autonomes utilisent déjà un autre serveur Edge Skype entreprise Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un message d’avertissement s’affiche pour vous informer sur l’autre serveur Edge et vous pouvez décider si vous voulez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
15. Cliquez sur **Terminer** dans l’écran suivant.
    
16. Vous pouvez maintenant publier cette technologie mise à jour, puis suivre les instructions de la rubrique [déploiement de serveurs Edge dans Skype entreprise Server](deploy-edge-servers.md) pour la déployer vers votre serveur de périphérie à partir de cet emplacement.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Définition de la topologie d’un pool de serveurs Edge équilibré de charge DNS

1. Connectez-vous à votre serveur Skype entreprise Server Standard Edition Server ou un serveur frontal Skype entreprise Server.
    
2. Ouvrez ensuite le **Générateur de topologie Skype entreprise Server**.
    
3. Dans l’arborescence de la console, développez le site sur lequel vous voulez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle réserve de périphérie**.
    
5. Cliquez sur **suivant** dans l’écran **définir un nouveau pool de bords** .
    
6. Dans l’écran **définir le nom de** domaine complet (FQDN) du pool de bords, tapez le nom de domaine complet (FQDN) interne que le pool de périphériques va utiliser, **puis cliquez sur** **suivant** lorsque vous avez fini.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
    - Vous pouvez utiliser les mêmes nom de domaine complet et adresse IP pour votre service d’accès SIP, votre service de conférence Web Skype entreprise Server et votre service Edge A/V. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
    - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
    - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Ce type d’utilisation est évident, que vous utilisiez une adresse IPv4 ou IPv6, et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez veiller à ce que vous deviez le garder à l’esprit pour l’étape 11). Vous avez également la possibilité de configurer votre serveur Edge ou votre pool Edge pour utiliser une adresse de traduction d’adresses réseau (NAT) pour l’adresse IP externe. Pour cela, activez la case à cocher **L’adresse IP externe de ce pool Edge est convertie par NAT**. Cliquez sur **Suivant** lorsque vous avez terminé.
    
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer votre nom de domaine complet unique dans la zone **accès SIP** . Ensuite, vous devez entrer des numéros de port différents pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer les trois noms de domaine complets (FQDN) externes pour le service **SIP Access** Edge, le service Edge de **conférence Web** et le service Edge **a/V** . Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Vous avez à présent atteint l’écran **définir les ordinateurs dans ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Dans cet exemple, entrez l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **adresse IPv6 interne** , en fonction des choix que vous avez effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon ce que vous utilisez) dans la zone de texte **accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d' **accès SIP** , le service Edge de **conférence Web** et le service Edge **A/V** , puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous venez de créer doit maintenant être répertorié dans la boîte de dialogue **définir les ordinateurs dans ce pool** .
    
14. Dans l’écran **définir les ordinateurs dans ce pool** , cliquez de nouveau sur le bouton **Ajouter** , puis répétez les étapes 11 à 13 jusqu’à ce que vous ayez ajouté tous les serveurs Edge dont vous avez besoin dans ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. Si vous avez opté pour une utilisation de la traduction d’adresses à l’étape 8, vous obtenez désormais un écran contenant une zone de texte d' **adresse IP publique** . Vous devez entrer l’adresse IPv4 publique et/ou IPv6 que vous avez définie pour le service Edge A/V, qui sera traduite par tar. Cliquez ensuite sur **Suivant**.
    
16. L’écran suivant permet **de définir le saut suivant**. Dans la zone **réserve de prochains tronçons** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un réalisateur dans votre environnement, vous devez choisir le réalisateur. Then click **Next**.
    
17. Dans l’écran **Associate front end** , vous devez spécifier une ou plusieurs grappes internes, y compris des pools d’éditions frontales et des pools d’éditions standard, à associer à ce serveur Edge. Il suffit de sélectionner les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Pour garder à l’esprit les points suivants : si vos pools internes ou serveurs autonomes utilisent déjà un autre serveur Edge Skype entreprise Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un message d’avertissement s’affiche pour vous informer sur l’autre serveur Edge et vous pouvez décider si vous voulez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
18. Cliquez sur **Terminer** dans l’écran suivant.
    
19. Vous pouvez maintenant publier cette technologie mise à jour, puis suivre les instructions de la rubrique [déploiement de serveurs Edge dans Skype entreprise Server](deploy-edge-servers.md) pour la déployer vers votre serveur de périphérie à partir de cet emplacement.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Définition de la topologie d’un pool de serveurs Edge équilibré en charge matérielle

1. Connectez-vous à votre serveur Skype entreprise Server Standard Edition Server ou un serveur frontal Skype entreprise Server.
    
2. Ouvrez ensuite le **Générateur de topologie Skype entreprise Server**.
    
3. Dans l’arborescence de la console, développez le site sur lequel vous voulez déployer le serveur Edge.
    
4. Cliquez avec le bouton droit sur **pools de bords**, puis cliquez sur **nouvelle réserve de périphérie**.
    
5. Cliquez sur **suivant** dans l’écran **définir un nouveau pool de bords** .
    
6. Dans l’écran **définir le nom de** domaine complet (FQDN) du pool de bords, tapez le nom de domaine complet (FQDN) interne que le pool de périphériques va utiliser, **puis cliquez sur** **suivant** lorsque vous avez fini.
    
7. Dans l’écran **Sélectionner les fonctionnalités**, vous disposez de plusieurs options :
    
   - Vous pouvez utiliser les mêmes nom de domaine complet et adresse IP pour votre service d’accès SIP, votre service de conférence Web Skype entreprise Server et votre service Edge A/V. Dans ce cas, vous devez cocher la case **Utiliser un seul nom de domaine complet et une seule adresse IP** (en gardant ceci à l’esprit pour l’étape 9 ci-dessous).
    
   - Si vous envisagez d’activer la fédération, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**.
    
8. Une fois que vous avez cliqué sur **Suivant**, l’écran **Options IP** qui s’affiche comporte les options suivantes :
    
   - Activer IPv4 sur l’interface interne
    
   - Activer IPv6 sur l’interface interne
    
   - Activer IPv4 sur l’interface externe
    
   - Activer IPv6 sur l’interface externe
    
     Ce type d’utilisation est évident, que vous utilisiez une adresse IPv4 ou IPv6, et que vous appliquiez ces adresses sur votre serveur Edge en interne ou en externe (vous devez veiller à ce que vous deviez le garder à l’esprit pour l’étape 11).
    
     > [!NOTE]
     > Contrairement aux deux autres options de topologie, lors de l’utilisation d’un dispositif d’équilibrage de la charge matérielle, vous **ne devez pas** sélectionner l’option **l’adresse IP externe du pool Edge est traduite par tar**. Cette opération n’est **pas prise en charge**.
  
9. Dans l’écran de noms de domaine complets externes, vos options dépendent de la sélection effectuée lors de l’étape 7 ci-dessus.
    
   - Si vous avez activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer votre nom de domaine complet unique dans la zone **accès SIP** . Ensuite, vous devez entrer des numéros de port différents pour chaque service Edge afin de leur permettre de se connecter de manière indépendante. Nous recommandons 5061 pour le service Edge d’**accès SIP**, 444 pour le service Edge de **conférence web** et 443 pour le service Edge **A/V**. Cliquez sur **Suivant** une fois que vous avez terminé.
    
   - Si vous n’avez pas activé la case à cocher **utiliser un nom de domaine complet et une adresse IP uniques** , vous devez entrer les trois noms de domaine complets (FQDN) externes pour le service **SIP Access** Edge, le service Edge de **conférence Web** et le service Edge **a/V** . Cliquez sur **Suivant** une fois que vous avez terminé.
    
10. Vous avez à présent atteint l’écran **définir les ordinateurs dans ce pool** . Cliquez sur le bouton **Ajouter**.
    
11. Vous êtes maintenant dans l’écran **définir l’adresse IP interne** . Dans cet exemple, entrez l’adresse IP de votre serveur Edge dans les zones de texte **adresse IPv4 interne** et **adresse IPv6 interne** , en fonction des choix que vous avez effectués à l’étape 8. Cliquez sur **Suivant** lorsque vous avez terminé.
    
12. Dans l’écran **Définir l’adresse IP externe**, vous disposez de plusieurs options selon vos sélections précédentes :
    
    - Vous utilisez peut-être un seul nom de domaine complet pour tous les services. Si tel est le cas, tapez votre adresse IPv4 ou IPv6 externe (selon ce que vous utilisez) dans la zone de texte **accès SIP** , puis cliquez sur **suivant**.
    
    - Vous avez peut-être choisi d’utiliser trois noms de domaine complets et adresses IP distincts pour les services. Si tel est le cas, entrez vos adresses IPv4 ou IPv6 externes pour le service Edge d' **accès SIP** , le service Edge de **conférence Web** et le service Edge **A/V** , puis cliquez sur **suivant**.
    
    > [!NOTE]
    > Si vous n’avez pas activé l’utilisation d’adresses IPv6 précédemment, cette boîte de dialogue ne s’affiche pas. Il s’agit d’un comportement normal et vous pouvez passer lors de l’étape suivante. 
  
13. Cliquez sur **Terminer**. Le serveur Edge que vous venez de créer doit maintenant être répertorié dans la boîte de dialogue **définir les ordinateurs dans ce pool** .
    
14. Dans l’écran **définir les ordinateurs dans ce pool** , cliquez de nouveau sur le bouton **Ajouter** , puis répétez les étapes 11 à 13 jusqu’à ce que vous ayez ajouté tous les serveurs Edge dont vous avez besoin dans ce pool. Lorsque cette opération terminée, cliquez sur **Suivant**.
    
15. L’écran suivant permet **de définir le saut suivant**. Dans la zone **réserve de prochains tronçons** , sélectionnez le nom de votre pool interne, qui peut être un pool frontal ou un pool autonome. Si vous avez un réalisateur dans votre environnement, vous devez choisir le réalisateur. Then click **Next**.
    
16. Dans l’écran **Associate front end** , vous devez spécifier une ou plusieurs grappes internes, y compris des pools d’éditions frontales et des pools d’éditions standard, à associer à ce serveur Edge. Il suffit de sélectionner les noms des pools internes que vous souhaitez utiliser pour communiquer avec les utilisateurs externes pris en charge. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > Pour garder à l’esprit les points suivants : si vos pools internes ou serveurs autonomes utilisent déjà un autre serveur Edge Skype entreprise Server, ils ne peuvent pas avoir plusieurs associations. Si vous choisissez un pool interne ou un serveur autonome dans cette situation, un message d’avertissement s’affiche pour vous informer sur l’autre serveur Edge et vous pouvez décider si vous voulez continuer ou non. Si vous poursuivez avec cette nouvelle association, la connexion à l’autre serveur Edge s’arrête. 
  
17. Cliquez sur **Terminer** dans l’écran suivant.
    
18. Vous pouvez maintenant publier cette technologie mise à jour, puis suivre les instructions de la rubrique [déploiement de serveurs Edge dans Skype entreprise Server](deploy-edge-servers.md) pour la déployer vers votre serveur de périphérie à partir de cet emplacement.
    
## <a name="publish-your-edge-server-topology"></a>Publication de votre topologie de serveur Edge

Une fois que vous avez terminé les étapes décrites ci-dessus, il est temps de publier cette nouvelle topologie, qui vous permettra également de l’exporter vers votre serveur Edge ou votre pool de serveurs Microsoft Skype entreprise Server. Procédez comme suit :
  
1. Lancez le **générateur de topologie** (s’il n’a pas déjà été lancé au cours de la procédure précédente).
    
2. Dans le **Générateur de topologie**, dans l’arborescence de la console, cliquez avec le bouton droit sur **Skype entreprise Server** , puis cliquez sur **Générateur de topologie Skype entreprise Server**.
    
3. Dans la page **Bienvenue** de l’Assistant, cliquez sur **Suivant**.
    
4. Dans la page **Créer d’autres bases de données**, cliquez sur **Suivant**.
    
5. Dès que l’état indique que la base de données a été correctement créée, procédez comme suit :
    
    - Pour afficher le journal, cliquez sur **Afficher le journal**.
    
    - Pour fermer l’Assistant, cliquez sur **Terminer**.
    
## <a name="export-your-edge-server-topology"></a>Exportation de votre topologie de serveur Edge

Pour que le déploiement réussisse, l’Assistant Déploiement de Skype entreprise Server a besoin d’accéder aux données du magasin central de gestion. Pour les serveurs internes de votre domaine ou de votre forêt, ceci est généralement simple. Les serveurs de périphérie se trouvant hors du domaine, il est nécessaire d’exporter manuellement le fichier de topologie vers l’emplacement du serveur de périphérie, en général sur un média physique. Cette exportation s’effectue via PowerShell :
  
1. Démarrez **Skype entreprise Server Management Shell**.
    
2. Dans **Skype entreprise Server Management Shell**, exécutez la commande suivante :
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Copiez le fichier exporté sur le média externe (par exemple, un lecteur USB ou un partage réseau que vous pouvez joindre à partir de l’emplacement du serveur Edge).
    

