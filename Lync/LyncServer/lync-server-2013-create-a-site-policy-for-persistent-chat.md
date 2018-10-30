---
title: "Lync Server 2013 : Créa. d’une strat. de site pour la conversation permanente"
TOCTitle: Création d’une stratégie de site pour la conversation permanente
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204693(v=OCS.15)
ms:contentKeyID: 49296327
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création d’une stratégie de site pour la conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site.

La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.

> [!NOTE]  
> Pour configurer et utiliser le serveur de conversations permanentes, vous devez d’abord utiliser le Générateur de topologie pour ajouter la prise en charge du serveur de conversations permanentes à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</a> dans la documentation de déploiement.<br />
Pour configurer les paramètres de configuration du serveur de conversations permanentes, reportez-vous à <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configuration des options de serveur de conversation permanente au niveau global ou pour un pool de serveurs de conversation permanente dans Lync Server 2013</a> dans la documentation de déploiement.

## Pour créer une stratégie de conversation permanente pour un site

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer**, sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **conversation permanenteStratégie**.
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

4.  Cliquez sur **Nouveau**, puis sur **Stratégie de site**.

5.  Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.

6.  Dans **Nouvelle stratégie conversation permanente**, effectuez les opérations suivantes :
    
      - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, Redmond).
    
      - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de salle de conversation pour Redmond).
    
      - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas spécifiquement contrôlés via une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.

7.  Cliquez sur **Valider**.

