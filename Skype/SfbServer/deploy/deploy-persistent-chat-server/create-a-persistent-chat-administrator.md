---
title: Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé : Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: d483517afcb5d02667d431259f8a2e76804cc32b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894471"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype pour Business Server 2015.
  
Dans Skype pour Business Server, les utilisateurs effectuent des tâches spécifiques doivent être attribués en tant que membres d’un ou plusieurs des groupes spécifiques. Contrôle d’accès basé sur un rôle (RBAC) est utilisée pour accorder des privilèges en assignant des utilisateurs à Skype prédéfini pour les rôles d’administration Business Server. Ces rôles correspondent aux groupes de sécurité universels dans les Services de domaine Active Directory. Les membres du groupe de sécurité administrateur de conversation permanente, CsPersistentChatAdministrator, autorisés à accéder aux applets de commande du serveur de conversation permanente, qui peuvent être exécutées à l’aide de la Skype pour Business Server Management Shell ou le Skype pour les entreprises Panneau de configuration de serveur.
  
Avant de configurer et d’administrer le serveur de conversations permanentes, assurez-vous que les autorisations et droits d’utilisateur ont été correctement définis, et que les utilisateurs possédant le rôle d’administrateur de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.
  
> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

Pour ajouter un utilisateur au groupe de sécurité administrateur de conversation permanente, CsPersistentChatAdministrator, effectuez les opérations suivantes :
  
1. En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.
    
2. Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.
    
3. Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.
    
4. Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.
    
5. Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.
    
6. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur OK.
    
7. Dans la boîte de dialogue Propriétés, cliquez sur OK.
    

