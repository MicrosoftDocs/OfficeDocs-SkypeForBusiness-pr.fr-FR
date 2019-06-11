---
title: 'Lync Server 2013 : Configuration des catégories'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configuration des catégories dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la section **catégorie** de la page de **conversation permanente** pour configurer les catégories. Une catégorie de salles de conversation permanente est une structure logique d’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.

Les catégories de salle de conversation pourront contenir des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que nom et description. De plus, la catégorie dispose de propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui en dépendent, par exemple si les salles de conversation autorisent les invitations ou les téléchargements de fichiers, ou qui contiennent l’historique de vos conversations.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

1.  À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des cmdlets Windows PowerShell. Pour plus d’informations, reportez-vous à <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.

4.  Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.

5.  Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent sur lequel la catégorie doit être créée. Le service est le pool de serveurs de chat permanent que le client de chat permanent utilise pour identifier le regroupement auquel la catégorie appartient. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de chat permanent et ne peut pas être déplacée vers une autre liste ou partagée avec un autre.

6.  Dans **Nouvelle catégorie**, procédez comme suit :
    
    1.  Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
    2.  Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
    3.  Pour déterminer si les invitations peuvent être activées pour des salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **activer** les invitations. Si cette option est sélectionnée, les salles de cette catégorie peuvent avoir des invitations activées ou désactivées; Si cette option est désactivée, les salles de cette catégorie ne peuvent pas avoir d’invitations. Si une salle est dotée d’invitations à l’ajout d’un nouveau membre, ce dernier reçoit une notification de la nouvelle salle dans le client de chat permanent.
    
    4.  Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe précédents qui utilisent Office&nbsp;Communications Server 2007 R2 Server Chat Server ou Lync Server 2010, une discussion de groupe peut publier des fichiers dans une salle. Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent.

        
        </div>
    
    5.  Pour contrôler l’historique des conversations, cochez ou décochez la case **activer l’historique des conversations** . Si cette option est sélectionnée, les conversations de la salle deviennent permanentes; dans le cas contraire, les messages ne sont pas conservés. Si la conformité est activée, les discussions sur place seront enregistrées en conformité, mais les utilisateurs ne seront pas en mesure d’accéder à d’anciens messages. Cette option peut être utilisée pour les salles destinées à des réunions ad hoc en temps réel, qui n’ont pas besoin de l’historique des discussions pour être persistants.

7.  Dans **Modifier la catégorie**, procédez comme suit :
    
      - Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux services de domaine Active Directory (utilisateurs, groupes de distribution, unités organisationnelles, etc.) qui sont autorisés à être ajoutés en tant que membres de salles de conversation. appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
      - Dans **appartenance**(membership), dans la section **membres refusés** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées aux membres refusés à partir de la salle.
    
      - Dans **appartenance**, dans la section **créateurs** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées à des créateurs pour la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.

8.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

