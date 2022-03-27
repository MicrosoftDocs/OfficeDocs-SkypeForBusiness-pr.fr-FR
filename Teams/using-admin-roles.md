---
title: Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
- seo-marvel-apr2020
ms.reviewer: islubin
description: Découvrez comment utiliser les rôles d’administrateur pour désigner les administrateurs qui ont besoin de différents niveaux d’accès pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c227abe677d75d06fd6577ccbfc8057c82f00002
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456957"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams

En utilisant Azure Active Directory (Azure AD), vous pouvez désigner les administrateurs qui ont besoin de différents niveaux d’accès pour la gestion des Microsoft Teams. Les administrateurs peuvent gérer la charge de travail de l’ensemble Teams charge de travail ou ils peuvent avoir des autorisations déléguées pour résoudre les problèmes de qualité des appels ou gérer les besoins téléphoniques de votre organisation.

## <a name="teams-roles-and-capabilities"></a>Teams rôles et fonctionnalités

Plusieurs rôles d’administrateur de Teams sont disponibles : administrateur de Teams, administrateur des communications Teams, spécialiste du support des communications Teams, ingénieur du support des communications Teams et administrateur de périphériques Teams. Examinez le tableau suivant pour comprendre ce que chaque rôle peut faire et les outils que l’administrateur peut utiliser dans le Microsoft Teams d’administration et PowerShell.

> [!NOTE]
> Skype Entreprise les administrateurs en ligne peuvent gérer les stratégies d’application **Teams** et **Skype Entreprise Online** via PowerShell.

Pour continuer, vous devez être administrateur. Les instructions pour obtenir les autorisations sont dans cet article.

<!-- add Global admin role? -->

| Rôle                                    | Peut effectuer ces tâches                                                           | Peut accéder aux outils suivants                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrateur Teams             | Gérez le service Teams, gérez et créez des groupes Microsoft 365'équipe.        | Tout ce qui se Microsoft Teams centre d’administration et les contrôles PowerShell associés, notamment :<ul><li> Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,2</sup></li><li>Gérer la voix, y compris les stratégies d’appel, l’inventaire des numéros de téléphone et l’affectation. <sup>1,3</sup></li><li>Gérer la messagerie, y compris les stratégies de messagerie. <sup>1,2</sup></li><li>Gérez tous les paramètres à l’échelle de l’organisation, y compris la fédération, la mise à niveau des équipes et les paramètres du client Teams. <sup>1,2</sup></li><li>Gérez les équipes de l’organisation et leurs paramètres associés, notamment l’appartenance (gestion des groupes prise en charge via PowerShell, gestion des équipes dans le Teams d’administration).<sup> 1,2</sup></li><li>Gérez Teams certifiés, et définissez et attribuez des stratégies de configuration.<sup> 1</sup></li><li>Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide d’outils de dépannage avancés. <sup>2</sup> </li><li>Accéder à tous les rapports dans le Centre Microsoft Teams’administration</li><li> Accédez, surveillez et dépannage la qualité et la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. Créez de nouveaux rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels selon vos besoins. Télécharger mettre à jour les données de création du CQD.</li><li> [Publier des applications dans le catalogue d’applications client dans le Centre Microsoft Teams’administration](manage-apps.md)</li></ul> |
| Administrateur des communications Teams      | Gérez les fonctionnalités d’appel et de réunion au sein Teams service.               | Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,2</sup><br><br> Gérer la voix, y compris les stratégies d’appel, l’inventaire des numéros de téléphone et l’affectation. <sup>1,3</sup><br><br> Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide duet d’outils de dépannage avancés. <sup>2</sup> <br><br> Accédez, surveillez et dépannage la qualité et la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. Créez de nouveaux rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels selon vos besoins. Télécharger mettre à jour les données de création du CQD.|
| Ingénieur du support technique pour les communications Teams   | Résolution des problèmes de communication au sein Teams l’aide **d’outils** avancés. | Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide d’outils de dépannage avancés. <sup>2</sup> <br><br> Accédez, surveillez et dépannage la qualité et la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. |
| Teams du support technique pour les communications | Résolution des problèmes de communication au sein Teams l’aide **d’outils de** base.    | Accédez à la page de profil utilisateur pour la résolution des problèmes d’appels dans l’analyse des appels. Peut uniquement afficher les informations de l’utilisateur spécifique recherché. <sup>2</sup> <br><br> Accédez, surveillez et dépannage de la qualité et de la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels. |
| Teams de périphériques              | Gérez les appareils configurés pour une utilisation avec le service Teams service.                    | Gérez la configuration et les mises à jour des appareils, examinez l’état et l’état des périphériques connectés, définissez et appliquez des profils de configuration, et redémarrez des appareils.<p>Le Teams administrateur de périphérique ne permet pas d’accéder aux données de qualité des appels ou à l’analyse des appels. Pour afficher les données de qualité des appels ou l’analyse des appels, vous devez avoir le rôle Teams de l’administrateur des communications. |

<sup>1</sup> [PowerShell - Microsoft Teams (](https://www.powershellgallery.com/packages/MicrosoftTeams/)la version publique 1.1.6 ou ultérieure est intégrée à Skype Entreprise Online Connector.)<br>
<sup>2 Microsoft Teams</sup> [centre d’administration3](./manage-teams-skypeforbusiness-admin-center.md)
 Teams compte d’administrateur doivent avoir une licence de licence Teams valide.<sup></sup>
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Pour plus d’informations sur les outils d’administration disponibles pour la gestion des Microsoft Teams, voir [Gestion des Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Pour plus d’informations sur les limites, spécifications et autres exigences qui s’appliquent Teams, voir [Limites et spécifications pour Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Attribuer des utilisateurs à chaque rôle

Vous pouvez attribuer ces rôles aux utilisateurs dans Azure AD. Pour découvrir comment attribuer des rôles d’administrateur à un utilisateur dans Azure AD, voir Affecter un utilisateur à des rôles d’administrateur [dans Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles pour chaque rôle

La plupart des outils PowerShell pour ces rôles d’administrateur sont disponibles dans le module Teams PowerShell. Il est important de noter que certains des cmdlets que ces rôles d’administrateur ont accès aux paramètres partagés qui sont également utilisés pour Skype Entreprise Online. 

Pour afficher la liste complète des cmdlets :

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Articles connexes

- [Microsoft Teams vue d’ensemble de PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](./assign-roles-permissions.md)
