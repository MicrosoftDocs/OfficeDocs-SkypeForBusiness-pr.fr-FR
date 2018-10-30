---
title: "Lync Server 2013 : Conf. de la strat. globale pour la conversation permanente"
TOCTitle: Configuration de la stratégie globale pour la conversation permanente
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204951(v=OCS.15)
ms:contentKeyID: 49297388
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la stratégie globale pour la conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Vous pouvez utiliser la stratégie globale par défaut par elle-même pour activer les paramètres de conversation permanente pour tous les utilisateurs dans votre déploiement. Vous pouvez également spécifier des stratégies supplémentaires pour les sites et les utilisateurs afin de contrôler si la conversation permanente est activée ou désactivée pour des utilisateurs et des sites spécifiques.

Il est impossible de supprimer la stratégie globale. Si vous essayez de la supprimer, les valeurs par défaut de la configuration sont rétablies.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.<br />
Pour configurer les paramètres de configuration du serveur de conversations permanentes, reportez-vous à <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement.

## Pour configurer la stratégie globale pour la conversation permanente

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer**, sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations.
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans Panneau de configuration Lync Server, cliquez sur **conversation permanente**, puis sur **Stratégie conversation permanente**.

4.  Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
      - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.
    
      - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, Stratégie globale pour *nom\_site\_central* ).
    
      - Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente**.

6.  Cliquez sur **Valider**.

