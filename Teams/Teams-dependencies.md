---
title: Autoriser l'accès invité dans Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.reviwer: laal
description: Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe399bb7b28f834575aeff344ff3fc4cca1b5dae
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autoriser l'accès invité dans Microsoft Teams
===========================================

Pour vous conformer aux exigences de votre organisation, vous pouvez gérer les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents. Tous les niveaux d’autorisation s’appliquent à votre client Office 365. Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :
- **Azure Active Directory** : l’accès invité dans Microsoft Teams repose sur la plate-forme entre entreprises (B2B) Azure AD. Contrôle l’expérience utilisateur au niveau du répertoire, du client et de l’application. 
- **Microsoft Teams** : contrôle uniquement Microsoft Teams. 
- **Groupes Office 365** : contrôle l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.
- **SharePoint Online et OneDrive Entreprise** : contrôle l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.

Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation. Par exemple, si vous ne souhaitez pas autoriser d’utilisateurs invités dans votre organisation Microsoft Teams, il vous suffit de désactiver l’accès invité dans Microsoft Teams. Autre exemple : vous pourriez activer l’accès invité aux niveaux AAD, des équipes et des groupes, puis désactiver l’ajout d’utilisateurs invités au niveau des équipes sélectionnées qui correspondent à un ou plusieurs critères, comme par exemple une classification des données confidentielles. Et vous n’utilisez peut-être pas de groupes Office 365. SharePoint Online et OneDrive Entreprise ont leurs propres paramètres d’accès invité qui ne reposent pas sur des groupes Office 365. 

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

  Le diagramme suivant montre comment la dépendance des autorisations de l’accès invité est octroyée et intégrée entre Azure Active Directory, Microsoft Teams et Office 365.


![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)


##<a name="azure-active-directory"></a>Azure Active Directory

Avec la collaboration entre entreprises (B2B) Azure AD, l’envoi d'invitations à des utilisateurs invités éventuels n’est pas restreint aux administrateurs de clients. Vous pouvez à la place utiliser des stratégies pour déléguer l’envoi des invitations aux utilisateurs dont les rôles les autorisent à envoyer des invitations.

Les paramètres des invitations s’appliquent au niveau du client et contrôlent l’expérience utilisateur au niveau du répertoire, du client et de l’application. Au minimum pour prendre en charge des invités, **peuvent inviter des membres** doit être définie à **Oui**.


![Capture d’écran des paramètres utilisateurs dans le portail Azure Active Directory.](media/teams_dependencies_image2.png)

Annonce Azure comprend les paramètres suivants pour configurer des utilisateurs externes :
- **Autorisations de l’utilisateur invité sont limitées**: **Oui** signifie que les invités n’ont l’autorisation pour certaines tâches de répertoire, tel que d’énumérer les utilisateurs, les groupes ou les autres ressources de répertoire. En outre, invités ne peut pas être affectées à des rôles administratifs dans votre répertoire. **No** signifie que vos invités disposent du même accès aux données de l’annuaire qui ont des utilisateurs normaux dans votre répertoire.
- **Administrateurs et utilisateurs dans le rôle d’émetteur de l’invitation invité peuvent inviter**: **Oui** signifie que les administrateurs et utilisateurs dans le rôle « Émetteur de l’invitation invité » sera en mesure d’invités au locataire. **No** signifie les administrateurs et les utilisateurs ne peuvent pas invités au locataire.
- **Les membres peuvent inviter**: **Oui** signifie que les membres non-admin de votre répertoire peuvent invités de collaborer sur les ressources sécurisées par votre annonce d’Azure, tels que les sites SharePoint ou ressources Azure. **No** signifie que seuls les administrateurs peuvent inviter vos invités dans votre répertoire.
- **Invités peuvent inviter**: **Oui** signifie qu’invités dans votre répertoire peuvent eux-mêmes inviter des autres invités pour collaborer sur des ressources sécurisées par votre annonce d’Azure, tels que les sites SharePoint ou ressources Azure. **No** signifie que vos invités ne peut pas inviter d’autres invités pour collaborer avec votre organisation.
 


> [!NOTE]
> Vous pouvez également gérer les domaines peuvent être invités à vos clients en tant qu’invités. Voir [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://technet.microsoft.com/library/a86bb46f-0e5b-43a3-b6ef-7394f344a8da). 

##<a name="microsoft-teams"></a>Microsoft Teams
Dans Microsoft Teams, vous pouvez contrôler si l’expérience invité est activée ou désactivée pour votre organisation. Ce paramètre est désactivé par défaut et s’applique au niveau du client pour Microsoft Teams uniquement.



Vous pouvez gérer l'accès invité dans Microsoft Teams via le centre d'administration d'Office 365. Pour plus d'informations, reportez-vous à la rubrique [Activer ou désactiver l'accès invité de Microsoft Teams](set-up-guests.md). 


##<a name="office-365-groups"></a>Groupes Office 365

À partir des groupes Office 365, vous pouvez contrôler l’ajout d’invités et l'accès invité à tous les groupes Office 365 et Microsoft Teams dans votre organisation.

1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
  
2. Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.
    
  
3. Sélectionnez **Groupes Office 365**.
    
     ![Groupes Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. Sur la page Groupes Office 365, définissez la bascule sur **Activé** ou **Désactivé**, pour autoriser ou non les propriétaires d'équipes et de groupes en dehors de votre organisation à accéder aux groupes Office 365. Définissez la bascule sur **Activé** près de l'option **Autoriser les propriétaires d'équipe à ajouter des personnes en dehors de l'organisation aux groupes**. Si vous définissez cette bascule sur Activé, une autre option vous permettant de contrôler si vous souhaitez autoriser ou non les propriétaires d’équipes et de groupes à ajouter des personnes externes à votre organisation aux groupes Office 365 et Microsoft Teams s’affiche. Définissez cette bascule sur Activé si vous souhaitez autoriser les propriétaires d'équipes et de groupes à ajouter des utilisateurs invités. ![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.


##<a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online et OneDrive Entreprise

Teams repose sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.  
  
    
    
Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :
  
    
    

- Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**
    
    Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**
    
    Pour plus d'informations, reportez-vous à la rubrique [Contrôler l'accès invité à Microsoft Teams](#controlguest).
  

Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.


Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).
