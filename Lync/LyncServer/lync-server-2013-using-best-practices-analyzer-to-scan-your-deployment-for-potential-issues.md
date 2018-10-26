---
title: "Ut. de Best Practices Analyzer pour rech. les pb éventuels ds votre déploiem."
TOCtitle: "Ut. de Best Practices Analyzer pour rech. les pb éventuels ds votre déploiem."
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg591343(v=OCS.15)
ms:contentKeyID: 49296192
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Utilisation de Best Practices Analyzer pour rechercher les problèmes éventuels dans votre déploiement

 

_**Dernière rubrique modifiée :** 2012-10-21_

Pour lancer une analyse Best Practices Analyzer, vous devez spécifier ce qui suit :

  - **Informations d’identification** Pour lancer une analyse, vous devez avoir ouvert une session sur un ordinateur, sur lequel Best Practices Analyzer est installé, avec un compte membre du groupe Administrateurs. En outre, ce compte doit disposer des droits et autorisations requis pour lancer les analyses appropriées ou vous devez spécifier des informations d’identification disposant des droits et autorisations appropriés pour exécuter Best Practices Analyzer. Pour plus d’informations, voir [Appartenances à des groupes et configuration requise des droits d’utilisateur pour Best Practices Analyzer](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).

  - **Étendue de l’analyse** Pour spécifier l’étendue de l’analyse, sélectionnez les catégories et les serveurs que vous voulez analyser. Vous pouvez sélectionner toutes les catégories, seulement certaines catégories ou certains serveurs dans une catégorie spécifique de votre environnement Lync Server.

  - **Type d’analyse** Actuellement, l’analyse de vérification de l’intégrité est le seul type d’analyse disponible (sélectionné par défaut). L’analyse de vérification de l’intégrité génère un rapport qui comprend les erreurs, les avertissements et d’autres informations pour tous les serveurs spécifiés dans l’étendue de l’analyse.

  - **Vitesse du réseau** Les options de vitesse du réseau sont LAN rapide (100 Mbps ou plus), LAN (10 Mbps), WAN rapide (1,5 Mbps) ou WAN (64 kbps). Le temps estimé pour réaliser l’analyse dépend de ce paramètre. Ce paramètre est également utilisé pour définir le délai d’expiration. Au cours de l’analyse, Best Practices Analyzer attend une réponse d’un serveur dans un délai spécifié. S’il ne reçoit aucune réponse dans ce délai, il passe au serveur suivant dans l’analyse. Sur les réseaux plus lents, ce délai est plus long pour prendre en compte les latences réseau plus longues. Nous vous recommandons de sélectionner la liaison la plus lente dans votre topologie pour ce paramètre afin que l’exécution de l’outil n’expire pas non plus.

## Pour analyser votre déploiement Lync Server 2013

1.  Ouvrez une session sur un ordinateur, sur lequel Best Practices Analyzer est installé, avec un compte membre du groupe Administrateurs local et qui dispose d’autres droits et autorisations requis.

2.  Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, cliquez sur **Microsoft Lync Server 2013**, puis sur **Best Practices Analyzer**.

3.  Dans l’écran d’**accueil**, cliquez sur **Sélectionner des options pour une nouvelle analyse**.

4.  Dans la page **Connexion à Active Directory**, vérifiez le nom spécifié dans **Serveur Active Directory**, puis effectuez l’une des opérations suivantes :
    
      - Pour lancer une analyse avec les informations d’identification que vous avez utilisées pour ouvrir une session sur l’ordinateur, cliquez sur **Connexion au serveur Active Directory**.
    
      - Pour spécifier d’autres informations d’identification que celles que vous souhaitez utiliser pour les services de domaine Active Directory, les serveurs Edge ou les serveurs Exchange, cliquez sur **Afficher les options d’ouverture de session avancées**, activez les cases à cocher pour lesquelles des informations d’identification distinctes sont requises, spécifiez les informations d’identification pour chacune des cases à cocher activées, puis cliquez sur **Connexion au serveur Active Directory**.
    
    > [!NOTE]  
    > Avant de commencer l’analyse, Best Practices Analyzer effectue une vérification du réseau et des autorisations pour s’assurer que les informations d’identification spécifiées sont valides et qu’il peut se connecter aux services de domaine Active Directory. Si l’outil est exécuté sur un serveur de groupe de travail, il vérifie également qu’il peut se connecter aux serveurs Edge dans le réseau de périmètre (s’ils sont inclus dans l’analyse).

5.  Dans la page **Démarrer une nouvelle analyse Best Practices**, sélectionnez les options que vous souhaitez inclure dans l’analyse, spécifiez la vitesse du réseau, puis cliquez sur **Démarrer l’analyse**.

6.  Dans la page **Analyse terminée**, cliquez sur **Afficher un rapport de cette analyse**.

7.  Dans la page **Afficher le rapport Best Practices**, effectuez l’une des opérations suivantes :
    
      - Pour afficher les rapports dans une liste organisée par composant serveur, cliquez sur **Rapports de liste**, puis cliquez sur l’onglet **Tous les problèmes** ou sur l’onglet **Éléments d’information**.
    
      - Pour afficher les rapports sous forme d’une liste hiérarchique organisée par types de résultats, cliquez sur **Rapports d’arborescence**, puis cliquez sur l’onglet **Affichage détaillé** ou sur l’onglet **Affichage de synthèse**.
    
      - Pour afficher d’autres rapports, cliquez sur **Autres rapports**.
    
    > [!NOTE]  
    > Pour plus d’informations sur les rapports de Best Practices Analyzer et les problèmes qu’ils identifient, consultez les rubriques <a href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Affichage et utilisation des rapports créés par Best Practices Analyzer</a> et <a href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyse et résolution des problèmes identifiés par Best Practices Analyzer</a>.
