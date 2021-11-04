---
title: Complément de conversation permanente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Vous pouvez utiliser la section De la page Conversation permanente pour associer des URL à des salles de conversation permanente. Ces URL apparaissent dans le client dans la salle de conversation dans le volet d’extensibilité de conversation. Un administrateur doit ajouter des modules à la liste des modules et les créateurs/gestionnaires de salles de conversation doivent associer les salles à l’un des modules ajoutés pour que les utilisateurs voient cette mise à niveau dans leur client.
ms.openlocfilehash: 344568f1beeb9b3ecdf1b651879b4b278fe34b42
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764102"
---
# <a name="persistent-chat-add-in"></a>Complément de conversation permanente

Vous pouvez utiliser la section  **De la** page Conversation permanente pour associer des URL à des salles de conversation permanente. Ces URL apparaissent dans le client dans la salle de conversation dans le volet d’extensibilité de conversation. Un administrateur doit ajouter des modules à la liste des modules et les créateurs/gestionnaires de salles de conversation doivent associer les salles à l’un des modules ajoutés pour que les utilisateurs voient cette mise à niveau dans leur client.

Les compléments servent à étendre l’expérience dans la salle. Un add-in type peut inclure une URL pointant vers une application Silverlight qui intercepte lorsqu’un ticker de stock est publié dans une salle de conversation et affiche l’historique des actions dans le volet d’extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».

Pour créer des add-ins pour les salles de conversation permanente, voir [Configure add-ins for Persistent Chat rooms in Skype Entreprise Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si vous êtes administrateur de conversation permanente, vous pouvez créer des modules à l’aide du panneau de Windows PowerShell cmdlets.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Complément** :

- [Configurer des add-ins pour les salles de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Pour configurer des compléments pour des salles de conversation

Les listes suivantes décrivent les menus, commandes, champs et propriétés de la page.

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.

2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de contrôle, voir Outils d’administration [Open Lync Server.](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)

3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.

    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste finale.

4. Dans la page **Complément**, cliquez sur **Nouveau**.

5. Dans **Sélectionner un service,** sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous devez créer le add-in. Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.

6. Dans **Nouveau complément**, procédez comme suit :

   - Dans **Nom**, spécifiez un nom pour le nouveau complément.

   - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.

7. Cliquez sur **Valider**.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir [Plan for Persistent Chat Server in Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype Entreprise Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [Manage Persistent Chat Server in Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).