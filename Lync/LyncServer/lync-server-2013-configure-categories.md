---
title: 'Lync Server 2013 : Configuration des catégories'
TOCTitle: Configuration des catégories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204859(v=OCS.15)
ms:contentKeyID: 49297062
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des catégories dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

Dans le Panneau de configuration Lync Server 2013, vous pouvez utiliser la section **Catégorie** de la page **conversation permanente** afin de configurer des catégories. Une catégorie de salle de conversation permanente est une structure logique permettant d’organiser des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et groupes d’utilisateurs autorisés à créer ou rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes subdivisions au sein de leurs organisations.

Les catégories des salles de conversation peuvent contenir des salles de conversation mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, par exemple, *Nom* et *Description* . En outre, la catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qu’elle contient. Par exemple, les salles de conversation peuvent autoriser les *invitations* ou les *téléchargements de fichiers* , ou contenir un *historique des conversations* .

## Pour configurer les catégories des salles de conversation

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer**, sélectionnez le Panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de démarrer le Panneau de configuration Lync Server, reportez-vous à [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).
    
    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell</a> dans la documentation de déploiement.

3.  Dans la barre de navigation de gauche, cliquez sur **conversation permanente**, puis sur **Catégorie**.
    
    Pour plusieurs déploiements de pool de serveurs de conversations permanentes, sélectionnez le pool approprié dans la liste déroulante.

4.  Dans la page **Catégorie**, cliquez sur **Nouvelle** ou **Modifier**.

5.  Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversations permanentes dans lequel la catégorie doit être créée. Le service correspond au pool de serveur de conversations permanentes que la conversation permanente (client) utilise pour identifier le pool auquel la catégorie appartient. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de conversations permanentes et ne peut pas être déplacée vers un autre pool, ni partagée avec un autre pool.

6.  Dans **Nouvelle catégorie**, procédez comme suit :
    
    1.  Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
    2.  Dans **Description**, fournissez une description détaillée de la catégorie de salle (exemple : catégorie de salle pour Contoso).
    
    3.  Pour déterminer si les invitations peuvent être activées pour les salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **Activer les invitations**. Si la case à cocher est activée, les salles de cette catégorie sont autorisées à avoir des invitations. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à avoir des invitations. Si une salle a des invitations et si un nouveau membre est ajouté à la salle, celui-ci reçoit une notification relative à la nouvelle salle dans son client de conversation permanente.
    
    4.  Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
        
        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur, car les applications personnalisées ou les clients antérieurs de Group Chat qui utilisent Office Communications Server 2007 R2, un serveur Group Chat ou Lync Server 2010, conversation de groupe peuvent publier des fichiers dans une salle. Comme le client Lync 2013 n’a aucune fonctionnalité de téléchargement, si vous disposez précisément d’un déploiement de Lync 2013 ou d’un client Lync 2013, vous ne pouvez pas publier de fichiers dans une salle de conversation d’un serveur de conversations permanentes.    
    5.  Pour contrôler l’historique des conversations, activez ou désactivez la case à cocher **Activer l’historique des conversations**. Si la case à cocher est activée, les conversations des salles deviennent permanentes ; sinon, les messages des conversations ne sont pas conservés. Si la conformité est activée, les conversations des salles sont enregistrées à des fins de conformité mais les utilisateurs ne peuvent pas accéder aux anciens messages. Cette option peut être utilisée pour les salles destinées aux collaborations en temps réel, ad hoc, qui n’ont pas besoin d’un historique des conversations permanent.

7.  Dans **Modifier la catégorie**, procédez comme suit :
    
      - Dans **Appartenance**, dans la section **Membres autorisés**, ajoutez ou supprimez les utilisateurs et autres principaux (utilisateurs, groupes de distribution, unités d’organisation, etc.) des services de domaine Active Directory qui peuvent être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
      - Dans **Appartenance**, dans la section **Membres refusés**, ajoutez ou supprimez les utilisateurs et autres principaux Active Directory associés aux membres dont l’accès à la salle est refusé.
    
      - Dans **Appartenance**, dans la section **Créateurs**, ajoutez ou supprimez les utilisateurs et autres principaux Active Directory associés aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.

8.  Cliquez sur **Valider**.

