---
title: Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé : Lisez cette rubrique pour découvrir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype Entreprise Server 2015.'
---

# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment créer un rôle d’administrateur de serveur de conversation permanente pour activer la configuration initiale et la gestion des services de conversation permanente dans Skype Entreprise Server 2015.
  
Dans Skype Entreprise Server, les utilisateurs qui effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs groupes spécifiques. Role-Based contrôle d’accès (RBAC) est utilisé pour accorder des privilèges en attribuant des utilisateurs à des rôles d’Skype Entreprise Server prédéfinés. Ces rôles correspondent aux groupes de sécurité universels dans les services de domaine Active Directory. Les membres du groupe de sécurité Administrateur de conversation permanente, CsPersistentChatAdministrator, ont accès aux cmdlets du serveur de conversation permanente, qui peuvent être exécutées à l’aide de l’Skype Entreprise Server Management Shell ou du Panneau de Skype Entreprise Server.
  
Avant de configurer et d’administrer le serveur de conversation permanente, assurez-vous que les droits et autorisations utilisateur appropriés sont en place et que tous les utilisateurs qui agiraient en tant qu’administrateurs de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.
  
> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Créer un administrateur de conversation permanente

Pour ajouter un utilisateur au groupe de sécurité Administrateur de conversation permanente, CsPersistentChatAdministrator, effectuez les étapes suivantes :
  
1. À l’aide d’un compte autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à un ordinateur sur lequel utilisateurs et ordinateurs Active Directory ont été installés.
    
2. Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.
    
3. Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.
    
4. Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.
    
5. Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.
    
6. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom complet de l’utilisateur à ajouter au groupe dans la zone Entrez les noms des objets à sélectionner, puis cliquez sur OK.
    
7. Dans la boîte de dialogue Propriétés, cliquez sur OK.
    

