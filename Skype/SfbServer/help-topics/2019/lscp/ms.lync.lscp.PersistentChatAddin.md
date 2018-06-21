---
title: Complément de conversation permanente
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Vous pouvez utiliser la section de la page de conversation permanente à associer les URL des salles de conversation permanente. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste des compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.
ms.openlocfilehash: 9aebe2f1bb1f17a562130e06e3c3030f533659b8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19964589"
---
# <a name="persistent-chat-add-in"></a>Complément de conversation permanente
 
Vous pouvez utiliser **la section de la page de **Conversation permanente** ** à associer les URL des salles de conversation permanente. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste des compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.
  
Les compléments servent à étendre l’expérience dans la salle. Un complément typique peut contenir une URL pointant vers une application Silverlight qui intercepte lorsqu’un téléscripteur est publié dans une salle de conversation et affiche l’historique des actions dans le volet de l’extensibilité. D’autres exemples incluent l’incorporation d’une URL OneNote dans la salle de conversation en tant que complément pour inclure un contexte partagé, tels que « Haut d’esprit » ou « Rubrique de la journée ».
  
Pour créer des compléments pour les salles de conversation permanente, consultez [configurer des compléments pour les salles de conversation permanente dans Skype pour Business Server 2015](../../../manage/persistent-chat/configure-add-ins.md). Si vous êtes un administrateur de conversation permanente, vous pouvez créer des compléments à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Complément**, vous pouvez effectuer les tâches suivantes :
  
- [Configurer des compléments pour les salles de conversation permanente Skype pour Business Server 2015](../../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a>Configuration des compléments pour des salles de conversation

Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration, voir [Ouvrir Outils d’administration Lync Server](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.
    
    Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.
    
4. Dans la page **Complément**, cliquez sur **Créer**.
    
5. Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous avez besoin pour créer le complément. Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.
    
6. Dans **Nouveau complément**, procédez comme suit :
    
  - Dans **Nom**, spécifiez un nom pour le nouveau complément.
    
  - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.
    
7. Cliquez sur **Valider**.
    
### 

Pour plus d’informations sur le serveur de conversation permanente des fonctionnalités, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer Persistent Chat Server dans Skype pour Business Server 2015](../../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanente dans Skype pour Business Server 2015](../../../manage/persistent-chat/persistent-chat.md).
  

