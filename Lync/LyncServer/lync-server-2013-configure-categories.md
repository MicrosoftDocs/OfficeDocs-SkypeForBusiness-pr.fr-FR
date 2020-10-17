---
title: 'Lync Server 2013 : configuration des catégories'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad435320a80b2cd2272fbe69afa59a79d39ccbd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521121"
---
# <a name="configure-categories-in-lync-server-2013"></a>Configurer des catégories dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la section **catégorie** de la page **conversation permanente** pour configurer des catégories. Une catégorie de salle de conversation permanente est une structure logique pour l’Organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et groupes d’utilisateurs autorisés à créer ou rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes subdivisions au sein de leurs organisations.

Les catégories de salle de conversation peuvent contenir des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que le nom et la description. De plus, la catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui lui appartiennent, par exemple si les salles de conversation autorisent les invitations ou les téléchargements de fichiers, ou si elles contiennent l’historique de conversation.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

1.  À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Vous pouvez également utiliser des applets de commande Windows PowerShell. Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.

    
    </div>

3.  Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.

4.  Dans la page **Catégorie**, cliquez sur **Nouvelle** ou **Modifier**.

5.  Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créée. Le service est le pool de serveurs de conversation permanente utilisé par la conversation permanente (client) pour identifier le pool auquel la catégorie appartient. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de conversation permanente et ne peut pas être déplacée vers une autre, ni partagée avec un autre pool.

6.  Dans **Nouvelle catégorie**, procédez comme suit :
    
    1.  Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
    2.  Dans **Description**, fournissez une description détaillée de la catégorie de salle (exemple : catégorie de salle pour Contoso).
    
    3.  Pour contrôler si les invitations peuvent être activées pour les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **activer les invitations** . Si cette option est sélectionnée, les salles de cette catégorie peuvent avoir des invitations. Si ce n’est pas le cas, les salles de cette catégorie ne sont pas autorisées à avoir des invitations. Si une salle comporte des invitations, lorsqu’un nouveau membre est ajouté à une salle, il obtient une notification de la nouvelle salle dans son client de conversation permanente.
    
    4.  Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
        
        <div>
        

        > [!IMPORTANT]  
        > Ce paramètre est appliqué sur le serveur car les applications personnalisées ou les clients de conversation de groupe précédents qui utilisent le serveur de conversation de groupe Office Communications Server 2007 R2 &nbsp; ou Lync server 2010 peuvent publier des fichiers dans une salle. Le client Lync 2013 ne dispose pas de la fonctionnalité de chargement/téléchargement de fichiers, de sorte que si vous avez un déploiement Lync 2013 pur ou un client Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation de serveur de conversation permanente.

        
        </div>
    
    5.  Pour contrôler l’historique de la conversation, activez ou désactivez la case à cocher **activer l’historique** de la conversation. Si la case à cocher est activée, les conversations des salles deviennent permanentes ; sinon, les messages des conversations ne sont pas conservés. Si la conformité est activée, les conversations des salles sont enregistrées à des fins de conformité mais les utilisateurs ne peuvent pas accéder aux anciens messages. Cette option peut être utilisée pour les salles destinées aux collaborations en temps réel, ad hoc, qui n’ont pas besoin d’un historique des conversations permanent.

7.  Dans **Modifier la catégorie**, procédez comme suit :
    
      - Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
      - Dans **appartenance**, dans la section **membres refusés** , ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés à des membres refusés de la salle.
    
      - Dans **appartenance**, dans la section **créateurs** , ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.

8.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

