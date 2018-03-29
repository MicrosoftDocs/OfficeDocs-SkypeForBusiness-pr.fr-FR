---
title: Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé : Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation persistant pour activer la configuration initiale et la gestion des services de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment créer un rôle d’administrateur de serveur de conversation persistant pour activer la configuration initiale et la gestion des services de conversation permanents dans Skype pour Business Server 2015.
  
Dans Skype pour Business Server, les utilisateurs effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs des groupes spécifiques. Contrôle d’accès basée sur les rôles (RBAC) est utilisé pour accorder des privilèges en assignant des utilisateurs à Skype prédéfini pour les rôles d’administration de serveur d’entreprise. Ces rôles correspondent aux groupes de sécurité universels dans les Services de domaine Active Directory. Les membres du groupe de sécurité administrateur de Chat persistant, CsPersistentChatAdministrator, autorisés à accéder à des applets de commande serveur de Chat persistant, qui peut être exécutée via la Skype pour Business Server Management Shell ou le Skype pour entreprise Panneau de configuration de serveur.
  
Avant de configurer et d’administrer le serveur de conversations permanentes, assurez-vous que les autorisations et droits d’utilisateur ont été correctement définis, et que les utilisateurs possédant le rôle d’administrateur de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.
  
## <a name="create-a-persistent-chat-administrator"></a>Créer un administrateur de conversation permanente

Pour ajouter un utilisateur au groupe de sécurité administrateur de Chat persistant, CsPersistentChatAdministrator, effectuez les opérations suivantes :
  
1. En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.
    
2. Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.
    
3. Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.
    
4. Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.
    
5. Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.
    
6. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur OK.
    
7. Dans la boîte de dialogue Propriétés, cliquez sur OK.
    

