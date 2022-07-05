---
title: Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Découvrez comment utiliser les rôles d’administration pour désigner des administrateurs qui ont besoin de différents niveaux d’accès pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17a8f6e9475355a5ee0f8960294bf3589d228ed1
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615450"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams

À l’aide d’Azure Active Directory (Azure AD), vous pouvez désigner des administrateurs qui ont besoin de différents niveaux d’accès pour gérer Microsoft Teams. Les administrateurs peuvent gérer l’ensemble de la charge de travail Teams, ou ils peuvent disposer d’autorisations déléguées pour résoudre les problèmes de qualité des appels ou gérer les besoins de téléphonie de votre organisation.

## <a name="teams-roles-and-capabilities"></a>Rôles et fonctionnalités Teams

Plusieurs rôles d’administrateur Teams sont disponibles : administrateur Teams, administrateur des communications Teams, spécialiste du support des communications Teams, ingénieur du support des communications Teams et administrateur d’appareils Teams. Passez en revue le tableau suivant pour comprendre ce que chaque rôle peut faire et les outils que l’administrateur peut utiliser dans le Centre d’administration Microsoft Teams et PowerShell.

> [!NOTE]
> Les administrateurs de Skype Entreprise Online peuvent gérer à la fois les stratégies des applications **Teams** et **Skype Entreprise Online** à travers PowerShell.

Pour suivre, vous devez être administrateur. Les instructions pour obtenir les autorisations figurent dans cet article.

<!-- add Global admin role? -->

| Rôle                                    | Peut effectuer ces tâches                                                           | Peut accéder aux outils suivants                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrateur Teams             | Gérez le service Teams et gérez et créez Groupes Microsoft 365.        | Tout ce qui se trouve dans le Centre d’administration Microsoft Teams et les contrôles PowerShell associés, notamment :<ul><li> Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,2</sup></li><li>Gérer la voix, y compris les stratégies d’appel et l’inventaire et l’affectation des numéros de téléphone. <sup>1,3</sup></li><li>Gérer la messagerie, y compris les stratégies de messagerie. <sup>1,2</sup></li><li>Gérez tous les paramètres à l’échelle de l’organisation, y compris la fédération, la mise à niveau des équipes et les paramètres client teams. <sup>1,2</sup></li><li>Gérez les équipes de l’organisation et leurs paramètres associés, y compris l’appartenance (gestion de groupe prise en charge via PowerShell, gestion d’équipe dans le Centre d’administration Teams). <sup>1,2</sup></li><li>Gérez les appareils certifiés Teams et configurez et attribuez des stratégies de configuration. <sup>1</sup></li><li>Affichez la page de profil utilisateur et résolvez les problèmes de qualité des appels utilisateur à l’aide de l’ensemble d’outils de dépannage avancé. <sup>2</sup> </li><li>Accéder à tous les rapports dans le Centre d’administration Microsoft Teams</li><li> Accédez, surveillez et résolvez les problèmes de qualité et de fiabilité des appels du locataire à l’aide des données exposées dans le tableau de bord de qualité des appels (CQD) aux utilisateurs affectés par une qualité d’appel médiocre. Créez des rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels en fonction des besoins. Chargez et mettez à jour les données de génération de CQD.</li><li> [Publier des applications dans le catalogue d’applications client dans le Centre d’administration Microsoft Teams](manage-apps.md)</li></ul> |
| Administrateur des communications Teams      | Gérer les fonctionnalités d’appels et de réunions dans le service Teams.               | Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,2</sup><br><br> Gérer la voix, y compris les stratégies d’appel et l’inventaire et l’affectation des numéros de téléphone. <sup>1,3</sup><br><br> Affichez la page de profil utilisateur et résolvez les problèmes de qualité des appels utilisateur à l’aide de l’ensemble d’outils de dépannage avancé. <sup>2</sup> <br><br> Accédez, surveillez et résolvez les problèmes de qualité et de fiabilité des appels du locataire à l’aide des données exposées dans le tableau de bord de qualité des appels (CQD) aux utilisateurs affectés par une qualité d’appel médiocre. Créez des rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels en fonction des besoins. Chargez et mettez à jour les données de génération de CQD.|
| Ingénieur du support technique pour les communications Teams   | Résolvez les problèmes de communication dans Teams à l’aide d’outils **avancés** . | Affichez la page de profil utilisateur et résolvez les problèmes de qualité des appels utilisateur à l’aide de l’ensemble d’outils de dépannage avancé. <sup>2</sup> <br><br> Accédez, surveillez et résolvez les problèmes de qualité et de fiabilité des appels du locataire à l’aide des données exposées dans le tableau de bord de qualité des appels (CQD) aux utilisateurs affectés par une qualité d’appel médiocre. |
| Spécialiste du support des communications Teams | Résolvez les problèmes de communication dans Teams à l’aide d’outils **de base** .    | Accédez à la page profil utilisateur pour résoudre les problèmes d’appels dans Call Analytics. Peut uniquement afficher les informations utilisateur pour l’utilisateur spécifique recherché. <sup>2</sup> <br><br> Accédez, surveillez et dépannez la qualité et la fiabilité des appels du locataire à l’aide des données exposées dans le tableau de bord de qualité des appels (CQD). |
| Administrateur d’appareils Teams              | Gérer les appareils configurés pour une utilisation avec le service Teams.                    | Gérez la configuration et les mises à jour des appareils, passez en revue l’intégrité et l’état des périphériques connectés, configurez et appliquez des profils de configuration, puis redémarrez les appareils.<p>Le rôle Administrateur d’appareils Teams ne fournit pas l’accès aux données de qualité des appels ou à l’analytique des appels. Pour afficher les données de qualité des appels ou l’analytique des appels, vous devez disposer du rôle Administrateur des communications Teams. |

<sup>1</sup> [Module PowerShell - Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/) (la version publique 1.1.6 ou ultérieure est intégrée à Skype Entreprise Connecteur en ligne.)<br>
<sup>2 Le</sup> compte d’administrateur du Centre 
[d’administration Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md)<sup>3</sup> Teams doit avoir une licence Teams valide.
<!-- <sup>3</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>4</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Pour plus d’informations sur les outils d’administration disponibles pour la gestion de Microsoft Teams, consultez [Gestion de Microsoft Teams](./manage-teams-skypeforbusiness-admin-center.md).

Pour plus d’informations sur les limites, les spécifications et d’autres exigences qui s’appliquent à Teams, consultez [Limites et spécifications pour Microsoft Teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Affecter des utilisateurs à chaque rôle

Vous pouvez affecter des utilisateurs à ces rôles dans Azure AD. Pour savoir comment attribuer des rôles d’administration à un utilisateur dans Azure AD, consultez [Affecter un utilisateur à des rôles d’administrateur dans Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Applets de commande disponibles pour chaque rôle

La plupart des outils PowerShell pour ces rôles d’administrateur résident dans le module Teams PowerShell, et il est important de noter que certaines des applets de commande auxquelles ces rôles d’administrateur ont accès pour contrôler les paramètres partagés qui sont également utilisés pour Skype Entreprise Online. 

Pour afficher la liste complète des applets de commande :

```powershell
Get-Command -Module MicrosoftTeams
 ```

### <a name="related-articles"></a>Articles connexes

- [Vue d’ensemble de Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](/powershell/module/teams/)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](./assign-roles-permissions.md)
