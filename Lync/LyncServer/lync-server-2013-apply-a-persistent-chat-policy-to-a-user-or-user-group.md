---
title: "Lync Server 2013 : Ap. d’une strat. de conv. perm. à un ut. ou à un gr. d’ut."
TOCTitle: Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205038(v=OCS.15)
ms:contentKeyID: 49297893
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Si un utilisateur a été activé pour Lync Server 2013, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques afin de les activer ou désactiver pour le serveur de conversations permanentes.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.<br />
Pour configurer les paramètres de configuration du serveur de conversations permanentes, reportez-vous à <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement.

Utilisez la procédure décrite dans cette rubrique pour appliquer une stratégie utilisateur de conversation permanente précédemment créée à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.

## Pour appliquer une stratégie utilisateur de conversation permanente à un compte d’utilisateur

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer**, sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server** sous **Stratégie conversation permanente**, sélectionnez la stratégie utilisateur conversation permanente à appliquer.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> appliquent la stratégie effective par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

6.  Cliquez sur **Valider**.

