---
title: Autoriser l'accès invité dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 04/01/19
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3e5f1ca3a00e8be43041db11133736256af4e48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885113"
---
<a name="authorize-guest-access-in-microsoft-teams"></a>Autoriser l'accès invité dans Microsoft Teams
===========================================

Pour vous conformer aux exigences de votre organisation, vous pouvez gérer les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents. Tous les niveaux d’autorisation s’appliquent à votre client Office 365. Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :

- **Azure Active Directory** : l’accès invité dans Microsoft Teams repose sur la plate-forme entre entreprises (B2B) Azure AD. Contrôle l’expérience utilisateur au niveau du répertoire, du client et de l’application. 
- **Microsoft Teams** : contrôle uniquement Microsoft Teams. 
- **Groupes Office 365** : contrôle l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.
- **SharePoint Online et OneDrive Entreprise** : contrôle l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.

Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation. Par exemple, si vous ne souhaitez pas autoriser d’utilisateurs invités dans votre Microsoft Teams mais que vous voulez les autoriser dans votre organisation, il vous suffit de désactiver l’accès invité dans Microsoft Teams. Autre exemple : vous pourriez activer l’accès invité aux niveaux AAD, des équipes et des groupes, puis désactiver l’ajout d’utilisateurs invités au niveau des équipes sélectionnées qui correspondent à un ou plusieurs critères, comme par exemple une classification des données confidentielles. SharePoint Online et OneDrive Entreprise ont leurs propres paramètres d’accès invité qui ne reposent pas sur des groupes Office 365. 

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019). 

Le diagramme suivant montre comment la dépendance des autorisations de l’accès invité est octroyée et intégrée entre Azure Active Directory, Microsoft Teams et Office 365.

![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)

Le diagramme suivant montre, à un haut niveau, comment l’expérience utilisateur fonctionne avec le modèle d’autorisation à travers un flux invitation et d’échange d’accès invité standard.

![Diagramme de flux d’invitation et d’échange](media/authorize-guest-image1.png)

Il est important de noter ici que les connecteurs, robots et applications peuvent nécessiter leur propre jeu d’autorisations et/ou consentement spécifiques aux comptes d’utilisateur. Il est possible qu’ils doivent être accordés séparément. De même, SharePoint impose peut-être des limites de partage externe supplémentaires pour un utilisateur spécifique, groupes d’utilisateurs, ou même au niveau du site.

Les deux diagrammes précédents sont également disponibles dans [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Contrôler l’accès invité dans Azure Active Directory

Utilisez Azure AD pour déterminer si des collaborateurs externes peuvent être invités à votre client en tant qu’invités, et de quelle façon. Pour plus d’informations sur Azure B2B, consultez [Qu’est-ce que l’accès utilisateur invité dans Azure Active Directory B2B ?](https://docs.microsoft.com/en-us/azure/active-directory/b2b/what-is-b2b). Pour plus d’informations sur les rôles d’Azure AD, voir [Accorder des autorisations aux utilisateurs des organisations partenaires dans votre client Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/b2b/add-guest-to-role).

Les paramètres des invitations s’appliquent au niveau du client et contrôlent l’expérience utilisateur au niveau du répertoire, du client et de l’application. Pour configurer ces paramètres dans le portail Azure, accédez à **Azure Active Directory** > **utilisateurs** > **les paramètres utilisateur**, sous **utilisateurs externes**, sélectionnez **Gérer les paramètres de collaboration externe**.

Azure AD inclut les paramètres suivants pour configurer des utilisateurs externes :

- **Autorisations des utilisateurs invités sont limitées**: **Oui** signifie que les invités ne sont pas autorisés à effectuer certaines tâches de répertoire, comme énumérer les utilisateurs, des groupes ou autres ressources de l’annuaire. En outre, les invités ne peut pas être affectées à des rôles d’administrateur dans votre annuaire. **Non** signifie que les invités ont le même accès aux données de l’annuaire que les utilisateurs normaux dans votre annuaire.
- **Les administrateurs et utilisateurs invités peuvent inviter**: **Oui** signifie que les administrateurs et utilisateurs dans le rôle « émetteur invité » peuvent ajouter des invités au client. **Non** signifie que les administrateurs et utilisateurs ne peuvent pas ajouter d’invités sur le client.
- **Les membres peuvent inviter**: **Oui** signifie que les membres non administrateurs de votre annuaire peuvent ajouter des invités pour collaborer sur des ressources sécurisées par votre Azure AD, par exemple, les sites SharePoint ou ressources Azure. **Non** signifie que seuls les administrateurs peuvent ajouter des invités à votre annuaire.</br>
      
    > [!NOTE]
    > Pour l’instant, Teams ne prend pas en charge le rôle émetteur de l’invitation. au minimum, le bouton bascule**Membres peuvent inviter** doit être défini sur **Oui** pour que l’accès invité fonctionne dans Teams.
- **Les invités peuvent inviter**: **Oui** signifie que les invités de votre annuaire peuvent ajouter des invités pour collaborer sur des ressources sécurisées par votre Azure AD, par exemple, les sites SharePoint ou ressources Azure. **Non** signifie que les invités ne peuvent pas inviter d’autres invités pour collaborer avec votre organisation.
 
Pour plus d’informations sur le contrôle qui peut invités, voir [invitations délégué pour la collaboration d’Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> Vous pouvez également gérer quels domaines peuvent être invités à votre client en tant qu’invités. Voir [Autoriser/bloquer l’accès invité aux groupes Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups). 

Ajouter manuellement le compte utilisateur invité à Azure AD B2B n’est pas obligatoire, comme le compte sera ajouté à l’annuaire automatiquement lorsque vous ajoutez les invités à Teams. 

La gestion des licences Azure AD permet d’ajouter jusqu’à 5 invités par licence. Pour plus d’informations sur les licences Azure AD, voir [Guide de licence de collaboration Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).

## <a name="control-guest-access-in-teams"></a>Gérer l'accès invité dans Microsoft Teams

Dans Teams, vous pouvez contrôler si l’expérience invité est activée ou désactivée pour votre organisation. Ce paramètre est désactivé par défaut et s’applique au niveau du client pour Microsoft Teams uniquement.

Vous pouvez gérer l'accès invité dans Teams via le centre d'administration Microsoft Teams. Pour plus d’informations, voir [Activer ou désactiver l’accès invité à Microsoft Teams](set-up-guests.md). 


## <a name="control-guest-access-in-office-365-groups"></a>Contrôler l’accès invité aux groupes Office 365

À partir des groupes Office 365, vous pouvez contrôler l’ajout d’invités et l'accès invité à tous les groupes Office 365 et Microsoft Teams dans votre organisation.

1. Connectez-vous avec votre compte d’administrateur général Office 365 dans [ https://portal.office.com/adminportal/home ](https://portal.office.com/adminportal/home).
    
2. Dans le menu de navigation, sélectionnez **Paramètres**, puis **Services &amp; compléments**.
    
3. Sélectionnez **Groupes Office 365**.
    
     ![Groupes Office 365](media/authorize-guest-image2.png)
  
4. Sur la page Groupes Office 365, définissez le bouton bascule sur **Activé** ou **Désactivé**, pour autoriser ou non les propriétaires d'équipes et de groupes en dehors de votre organisation à accéder aux groupes Office 365. Cliquez ou appuyez sur le bouton bascule **On** à côté de **Autoriser les propriétaires de groupe à ajouter des personnes externes à l’organisation à des groupes**. Si vous définissez ce bouton bascule sur**On**, une autre option vous permettant de contrôler si vous souhaitez autoriser ou non les propriétaires d’équipes et de groupes à ajouter des personnes externes à votre organisation aux groupes Office 365 et Microsoft Teams s’affiche. Définissez cette bascule sur**On** si vous souhaitez autoriser les propriétaires d'équipes et de groupes à ajouter des utilisateurs invités. 
 
   ![La capture d'écran illustre le panneau Groupes d'Office 365 avec les options activées pour permettre aux membres du groupe de l'extérieur de l'organisation d'accéder au contenu du groupe, et aux propriétaires d'ajouter au groupe des personnes externes à l'organisation.](media/authorize-guest-image3.png)

Les paramètres ci-dessus s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans les groupes Office 365 et Microsoft Teams.

Voir [Accès invité dans les groupes Office 365](https://support.office.com/en-us/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) pour plus d’informations sur l’accès invité dans les groupes, y compris comment l’accès invité fonctionne, comment gérer l’accès invité et Forum aux questions.

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a>Contrôler l’accès invité à SharePoint Online et OneDrive Entreprise

Teams repose sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.  
   
Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :

- Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**
    
    Pour obtenir plus d’informations, consultez l’article [Gérer le partage externe pour votre environnement SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).
    
- Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**
    
    Pour plus d'informations, voir[Contrôler l'accès invité aux groupes Office 365](#control-guest-access-in-office-365-groups)ci-dessus.
  
Ces paramètres s’appliquent au niveau du client et contrôlent l’expérience utilisateur dans SharePoint Online, OneDrive Entreprise, les groupes Office 365 et Microsoft Teams.

Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).

## <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
