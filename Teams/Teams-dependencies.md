---
title: Autoriser l'accès invité dans Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/26/18
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.
appliesto:
- Microsoft Teams
ms.openlocfilehash: be1aa39a73cf5c4a28866ac8b702afebeb992b0d
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753818"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autoriser l'accès invité dans Microsoft Teams
===========================================

Pour vous conformer aux exigences de votre organisation, vous pouvez gérer les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents. Tous les niveaux d’autorisation s’appliquent à votre client Office 365. Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :

- **Azure Active Directory** : l’accès invité dans Microsoft Teams repose sur la plate-forme entre entreprises (B2B) Azure AD. Contrôle l’expérience utilisateur au niveau du répertoire, du client et de l’application. 
- **Microsoft Teams** : contrôle uniquement Microsoft Teams. 
- **Groupes Office 365** : contrôle l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.
- **SharePoint Online et OneDrive Entreprise** : contrôle l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.

Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation. Par exemple, si vous ne voulez pas permettre aux utilisateurs dans votre Teams Microsoft, mais souhaitez autoriser globale de votre organisation, désactivez simplement l’accès invité dans Microsoft Teams. Autre exemple : vous pourriez activer l’accès invité aux niveaux AAD, des équipes et des groupes, puis désactiver l’ajout d’utilisateurs invités au niveau des équipes sélectionnées qui correspondent à un ou plusieurs critères, comme par exemple une classification des données confidentielles. SharePoint Online et OneDrive Entreprise ont leurs propres paramètres d’accès invité qui ne reposent pas sur des groupes Office 365. 

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

Le diagramme suivant montre comment la dépendance des autorisations de l’accès invité est octroyée et intégrée entre Azure Active Directory, Microsoft Teams et Office 365.

![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)

Le diagramme suivant illustre, à un niveau élevé, le fonctionne de l’expérience utilisateur avec le modèle d’autorisation via un flux d’accès invité ordinaires invitation et le remboursement.

![Diagramme de flux d’invitation et le remboursement](media/authorize-guest-image1.png)

Il est important de noter que robots, applications et les connecteurs peuvent exiger leur propre ensemble d’autorisations et/ou consentement spécifiques au compte d’utilisateur. Elles devront être accordées séparément. De même, SharePoint peut imposer très externes partage des limites pour un utilisateur spécifique, groupes d’utilisateurs, ou encore au niveau du site.

## <a name="control-guest-access-in-azure-active-directory"></a>Contrôler l’accès invité dans Azure Active Directory

Utilisez Azure AD pour déterminer si les collaborateurs externes peuvent être invités à votre client en tant qu’invités et de quelle manière. Pour plus d’informations sur l’accès invité B2B Azure, voir [Nouveautés de l’accès des utilisateurs invité dans Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b). Pour plus d’informations sur les rôles d’Azure AD, voir [accorder des autorisations aux utilisateurs d’organisations partenaires dans votre client Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).

Les paramètres des invitations s’appliquent au niveau du client et contrôlent l’expérience utilisateur au niveau du répertoire, du client et de l’application. 

![Capture d’écran des paramètres utilisateurs dans le portail Azure Active Directory.](media/teams_dependencies_image2.png)

Azure AD inclut les paramètres suivants pour configurer des utilisateurs externes :

- **Les autorisations utilisateur invité sont limitées**: **Oui** signifie que les invités n’autorisé pour certaines tâches de répertoire, énumérer tels que les utilisateurs, groupes ou autres ressources de répertoire. En outre, les invités ne peuvent pas être attribuées aux rôles d’administration dans votre répertoire. **No** signifie que les invités ont le même accès aux données dont les utilisateurs classiques dans votre répertoire de l’annuaire.
- **Administrateurs et aux utilisateurs dans le rôle d’émetteur de l’invitation invité peuvent inviter**: **Oui** signifie que les administrateurs et aux utilisateurs dans le rôle « Émetteur de l’invitation invité » sera en mesure d’invités au client. **No** signifie Administrateurs et les utilisateurs ne peuvent pas invités au client.
- **Les membres peuvent inviter**: **Oui** signifie que non-admin membres de votre annuaire peuvent invités à collaborer sur des ressources sécurisées par votre Azure AD, tels que les sites SharePoint ou ressources Azure. **No** signifie que seuls les administrateurs peuvent inviter invités dans votre répertoire.</br>
      
    > [!NOTE]
    > Actuellement, les équipes ne gère pas le rôle d’émetteur de l’invitation invité. au minimum les **membres peuvent inviter** bascule doit être définie sur **Oui** pour l’accès invité de travailler en équipe.
- **Les invités peuvent inviter**: **Oui** signifie que les invités dans votre répertoire peuvent eux-mêmes inviter autres invités à collaborer sur des ressources sécurisées par votre Azure AD, tels que les sites SharePoint ou ressources Azure. **No** signifie que les invités ne peut pas inviter d’autres invités pour collaborer avec votre organisation.
 
Pour plus d’informations sur le contrôle qui peut invités, voir [invitations délégué pour Azure Active Directory B2B collaboration](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> Vous pouvez également gérer les domaines peuvent être invités à votre client en tant qu’invités. Voir [Autoriser/bloquer l’accès invité à des groupes d’Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

Ajouter le compte d’utilisateur invité manuellement pour Azure AD B2B n’est pas obligatoire, comme le compte sera ajouté au répertoire automatiquement lorsque vous ajoutez l’invité aux équipes. 

Le Gestionnaire de licences Azure AD vous permet d’ajouter jusqu'à 5 invités par licence. Pour plus d’informations sur les licences d’Azure Active Directory, consultez les [instructions de gestion des licences de collaboration Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Contrôler l’accès invité dans les équipes

Dans les équipes, vous pouvez contrôler si l’expérience de l’invité est activé ou désactivé pour votre organisation. Le paramètre est désactivé par défaut et s’applique au niveau du client uniquement pour les équipes.

Vous pouvez gérer les paramètres d’accès aux équipes invité à partir du centre d’administration de Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Activer ou désactiver l'accès invité de Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Contrôler l’accès invité dans Office 365 groupes

À partir des groupes Office 365, vous pouvez contrôler l’ajout d’invités et l'accès invité à tous les groupes Office 365 et Microsoft Teams dans votre organisation.

1. Connectez-vous à l'aide de votre compte d'administrateur général Office 365 sur [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).
    
2. Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.
    
3. Sélectionnez **Groupes Office 365**.
    
     ![Groupes Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  
4. Dans la page groupes de Office 365, la valeur la bascule **ou **désactiver**,** selon que vous souhaitez laisser les propriétaires de groupe et de l’équipe en dehors de vos groupes d’accès Office 365 entreprise. Définissez la bascule sur **Activé** près de l'option **Autoriser les propriétaires d'équipe à ajouter des personnes en dehors de l'organisation aux groupes**. Si vous activez ce bouton **activé**, vous verrez une autre option pour contrôler si vous souhaitez que le groupe et les propriétaires de l’équipe ajouter des personnes extérieures à votre organisation aux groupes d’Office 365 et les équipes Microsoft. Définissez cette bascule **activé** si vous souhaitez que le groupe et les utilisateurs invités ajouter des propriétaires d’équipe. 
 
   ![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)

Ces paramètres s’appliquent au niveau du client et contrôlent l’expérience invité dans Office 365 groupes et Teams Microsoft.

Pour plus d’informations sur l’accès invité dans des groupes, y compris le fonctionnement de l’accès invité, la gestion des accès invité et des réponses aux questions fréquemment posées, consultez [invité accéder dans Office 365 groupes](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) .

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Contrôler l’accès invité à SharePoint Online et OneDrive entreprise

Teams repose sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.  
   
Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :

- Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**
    
    Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).
    
- Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**
    
    Pour plus d’informations, consultez [contrôler l’accès invité dans Office 365 groupes](#control-guest-access-in-office-365-groups), ci-dessus.
  
Ces paramètres s’appliquent au niveau du client et contrôlent l’expérience invité à SharePoint Online, OneDrive pour l’entreprise, Office 365 groupes et les équipes.

Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).

## <a name="guest-access-vs-external-access-federation"></a>Accès invité et l’accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]