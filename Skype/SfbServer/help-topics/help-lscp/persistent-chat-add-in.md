---
title: Complément de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Vous pouvez utiliser la section complément de la page de conversation permanente pour associer des URL à des salles de conversation permanentes. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste de compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.
ms.openlocfilehash: da971a43c8e113dc1fff8ee9dc600f55a2fea955
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686217"
---
# <a name="persistent-chat-add-in"></a>Complément de conversation permanente

Vous pouvez utiliser la section **complément** de la page de **conversation permanente** pour associer des URL à des salles de conversation permanentes. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste de compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.

Les compléments servent à étendre l’expérience dans la salle. Un complément classique peut inclure une URL pointant vers une application Silverlight qui intercepte quand un code d’action est publié dans une salle de conversation et affiche l’historique des actions dans le volet extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».

Pour créer des compléments pour des salles de conversation permanentes, voir [configurer des compléments pour les salles de conversation permanentes dans Skype entreprise Server 2015](../../manage/persistent-chat/configure-add-ins.md). Si vous êtes un administrateur de chat permanent, vous pouvez créer des compléments à l’aide du panneau de configuration ou des applets de commande Windows PowerShell.

## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Complément**, vous pouvez effectuer les tâches suivantes :

- [Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>Configuration des compléments pour des salles de conversation

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.

2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes permettant de lancer le panneau de configuration, reportez-vous à la rubrique [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).

3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.

    Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.

4. Dans la page **Complément**, cliquez sur **Créer**.

5. Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent pour lequel vous devez créer le complément. Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.

6. Dans **Nouveau complément**, procédez comme suit :

   - Dans **Nom**, spécifiez un nom pour le nouveau complément.

   - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.

7. Cliquez sur **Valider**.

## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de chat permanent, voir [planifier le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur de conversation permanente dans skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanent dans Skype entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).


