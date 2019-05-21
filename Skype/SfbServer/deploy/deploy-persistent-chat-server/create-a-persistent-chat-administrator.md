---
title: Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Résumé: cette rubrique vous explique comment créer un rôle d’administrateur serveur de chat permanent permettant de configurer et de gérer les services de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273881"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Pour plus d’informations sur la création d’un rôle d’administrateur de serveur de chat permanent, voir la rubrique Configuration initiale et gestion des services de chat permanent dans Skype entreprise Server 2015.
  
Dans Skype entreprise Server, les utilisateurs qui effectuent des tâches spécifiques doivent être affectés en tant que membres d’un ou plusieurs groupes spécifiques. Le contrôle d’accès basé sur les rôles (RBAC) permet d’accorder des privilèges en attribuant aux utilisateurs des rôles d’administrateur prédéfinis Skype entreprise Server. Ces rôles correspondent aux groupes de sécurité universelles dans les services de domaine Active Directory. Les membres du groupe de sécurité administrateur de chat permanent, CsPersistentChatAdministrator, ont accès aux cmdlets du serveur de chat permanent, qui peuvent être exécutées à l’aide de Skype entreprise Server Management Shell ou de Skype entreprise. Panneau de configuration du serveur.
  
Avant de configurer et d’administrer le serveur de conversations permanentes, assurez-vous que les autorisations et droits d’utilisateur ont été correctement définis, et que les utilisateurs possédant le rôle d’administrateur de conversation permanente sont ajoutés au groupe de sécurité Administrateur de conversation permanente.
  
> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

Pour ajouter un utilisateur au groupe de sécurité administrateur de conversations permanentes, CsPersistentChatAdministrator, procédez comme suit:
  
1. En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.
    
2. Cliquez sur Démarrer, sur Tous les programmes, sur Outils d’administration, puis sur Utilisateurs et ordinateurs Active Directory.
    
3. Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur Utilisateurs.
    
4. Cliquez avec le bouton droit sur le groupe de sécurité CsPersistentChatAdministrator, puis cliquez sur Propriétés.
    
5. Dans la boîte de dialogue Propriétés, sous l’onglet Membres, cliquez sur Ajouter.
    
6. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes, tapez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur OK.
    
7. Dans la boîte de dialogue Propriétés, cliquez sur OK.
    

