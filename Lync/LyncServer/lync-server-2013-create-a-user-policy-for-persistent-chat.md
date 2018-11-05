---
title: "Lync Server 2013 : Créa. d’une strat. ut. pour la conversation permanente"
TOCTitle: Création d’une stratégie utilisateur pour la conversation permanente
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205170(v=OCS.15)
ms:contentKeyID: 49298468
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Dans le Panneau de configuration Lync Server, vous définissez des stratégies utilisateur qui peuvent être affectées à des utilisateurs dans **Utilisateurs**.

La stratégie utilisateur supplante les stratégies globale et de site, mais uniquement pour les utilisateurs pour lesquels la stratégie utilisateur est appliquée.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.<br />
Pour configurer les paramètres de configuration du serveur de conversations permanentes, reportez-vous à <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement.

## Pour créer une stratégie utilisateur pour la conversation permanente

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer**, sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **Stratégie conversation permanente**.

4.  Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.

5.  Dans **Nouvelle stratégie conversation permanente**, effectuez les opérations suivantes :
    
      - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
      - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie de conversation permanente pour utilisateur spécifique).
    
      - Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente**

6.  Cliquez sur **Valider**.

