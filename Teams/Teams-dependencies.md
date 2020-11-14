---
title: Autoriser l'accès invité dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: Gérez les fonctionnalités d’accès invité dans Microsoft Teams par le biais de quatre niveaux d’autorisation différents.
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030990"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a>Autoriser l'accès invité dans Microsoft Teams

Pour répondre aux besoins de votre organisation, vous pouvez gérer les fonctionnalités et capacités d’accès invité des équipes par le biais de quatre niveaux d’autorisation différents. Tous les niveaux d’autorisation s’appliquent à votre organisation Microsoft 365. Chaque niveau d’autorisation contrôle l’expérience utilisateur comme indiqué ci-dessous :

- **Azure Active Directory** : l’accès invité dans teams repose sur la plateforme Azure ad Business-to-Business. Ce niveau d’autorisation contrôle l’expérience des utilisateurs au niveau de l’annuaire, du client et de l’application.
- **Équipes** : contrôle l’interface invité dans teams uniquement.
- **Groupes microsoft 365** : contrôle l’interface invité dans les groupes et équipes Microsoft 365.
- **SharePoint et onedrive** : contrôle l’interface utilisateur dans SharePoint, OneDrive, groupes Microsoft 365 et équipes.

Ces différents niveaux d’autorisation vous donnent de la flexibilité pour configurer l’accès invité pour votre organisation. Par exemple, si vous ne voulez pas autoriser les utilisateurs invités dans Microsoft Teams, mais que vous souhaitez leur accorder une autorisation globale au sein de votre organisation, il vous suffit de désactiver l’accès invité dans Teams. Voici un autre exemple : vous pouvez activer l’accès invité aux niveaux d’Azure AD, des équipes et des groupes, mais vous pouvez [également désactiver l’ajout d’utilisateurs invités à des équipes sélectionnées qui répondent à un ou plusieurs critères comme la classification des données est confidentiel](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites). SharePoint et OneDrive possèdent leurs propres paramètres d’accès invité qui ne dépendent pas de groupes Microsoft 365.

Pour obtenir des instructions de configuration de bout en bout, voir [collaborer avec des invités dans une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

> [!NOTE]
> Les invités sont soumis aux limites de service décrites dans [Descriptions des services Microsoft 365 et Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [limitations d’Azure AD B2B collaboration](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations). 

Le diagramme suivant montre comment une dépendance d’autorisation d’accès invité est accordée et intégrée entre Azure Active Directory, teams et Microsoft 365.

> [!div class="mx-imgBorder"]
> ![Diagramme des dépendances des autorisations de l’accès invité.](media/teams_dependencies_image1.png)

Le diagramme suivant montre, à un haut niveau, comment l’expérience utilisateur fonctionne avec le modèle d’autorisation à travers un flux invitation et d’échange d’accès invité standard.

> [!div class="mx-imgBorder"]
> ![Diagramme de flux d’invitation et d’échange](media/authorize-guest-image1.png)

Il est important de noter que les applications, robots et connecteurs peuvent nécessiter leur propre ensemble d’autorisations et/ou de consentement spécifiques au compte d’utilisateur. Il est possible qu’ils doivent être accordés séparément. De même, SharePoint impose peut-être des limites de partage externe supplémentaires pour un utilisateur spécifique, groupes d’utilisateurs, ou même au niveau du site.

Les deux diagrammes précédents sont également disponibles dans [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).

## <a name="control-guest-access-in-azure-active-directory"></a>Contrôler l’accès invité dans Azure Active Directory

Utilisez Azure AD pour déterminer si des collaborateurs externes peuvent être invités à votre client en tant qu’invités, et de quelle façon. Pour plus d’informations sur Azure B2B, consultez [Qu’est-ce que l’accès utilisateur invité dans Azure Active Directory B2B ?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b). Pour plus d’informations sur les rôles d’Azure AD, voir [Accorder des autorisations aux utilisateurs des organisations partenaires dans votre client Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).

Les paramètres des invitations s’appliquent au niveau de l’organisation et contrôlent l’interface utilisateur au niveau de l’annuaire et de l’application. Vous pouvez configurer ces paramètres dans les [paramètres de collaboration externes](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).

Azure AD inclut les paramètres suivants pour configurer des utilisateurs externes :

- [Restrictions d’accès des utilisateurs invités](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- **Les administrateurs et utilisateurs ayant le rôle d'Inviteur d’invités peuvent inviter**  : **Oui** signifie que les administrateurs et utilisateurs dans le rôle « Inviteur d’invités » peuvent ajouter des invités au client. **Non** signifie que les administrateurs et utilisateurs ne peuvent pas ajouter d’invités sur le client.
- **Les membres peuvent envoyer des invitations**  : pour autoriser les membres non administrateurs de votre annuaire à convier des invités, attribuez la valeur **Oui** (recommandé) à cette stratégie. Si vous préférez que seuls les administrateurs puissent ajouter des invités, vous pouvez affecter la valeur **Non** à cette stratégie. Ne pas oublier que le paramètre **Non** limite l’expérience invité aux propriétaires d’équipes non administrateurs ; ils ne pourront ajouter des invités dans Teams que si ceux-ci ont déjà été ajoutés par l'administrateur dans Azure Active Directory.
- **Les invités peuvent inviter**  : **Oui** signifie que les invités de votre annuaire peuvent ajouter des invités pour collaborer sur des ressources sécurisées par votre instance d’Azure AD, par exemple, les sites SharePoint ou les ressources Azure. **Non** signifie que les invités ne peuvent pas inviter d’autres invités pour collaborer avec votre organisation. Même si la valeur est définie sur **Yes** , Guest ne peut pas inviter d’autres invités dans Teams.
 
Pour plus d’informations sur le contrôle des personnes autorisées à inviter des invités, voir [activer la collaboration externe B2B et gérer qui peut inviter des personnes](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).

> [!NOTE]
> Vous pouvez également gérer quels domaines peuvent être invités à votre client en tant qu’invités. Reportez-vous à la rubrique [autoriser ou bloquer les invitations à des utilisateurs B2B d’organisations spécifiques](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).

Ajouter manuellement le compte utilisateur invité à Azure AD B2B n’est pas obligatoire, comme le compte sera ajouté à l’annuaire automatiquement lorsque vous ajoutez les invités à Teams.

### <a name="licensing-for-guest-access"></a>Gestion des licences pour l’accès invité

La gestion des licences d’accès invité utilise le prix d’identités externes d’Azure AD et repose sur des invités actifs mensuels. Pour plus d’informations, voir [modèle de facturation pour les identités externes d’Azure ad](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) .

> [!NOTE]
> Les utilisateurs de votre organisation qui ont uniquement des offres d’abonnement Office 365 autonomes, telles que Exchange Online Plan 2, ne peuvent pas être invités en tant qu’invités à votre organisation, car les équipes considèrent ces utilisateurs comme membres de la même organisation. Pour que ces utilisateurs puissent utiliser des équipes, une offre Microsoft 365 Business Standard, Office 365 Entreprise ou Office 365 Éducation doivent leur être attribuée. 

## <a name="external-access-federation-vs-guest-access"></a>Accès externe (fédération) et accès invité

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a>Voir aussi

- [Références sur les paramètres de partage d’invités de Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[Configurer la collaboration sécurisée avec Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
