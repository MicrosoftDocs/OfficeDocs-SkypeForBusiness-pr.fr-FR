---
title: Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams
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
ms.openlocfilehash: 637d6e63b0eabdc9517e8d5cd5986ae7661ad118
ms.sourcegitcommit: 032a22c8b61456dcbd798ec390f0ae1ca7d8eda0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357612"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Utiliser les rôles d’administrateur Microsoft Teams pour gérer Teams

En utilisant Azure Active Directory (Azure AD), vous pouvez désigner les administrateurs qui ont besoin de différents niveaux d’accès pour la gestion de Microsoft Teams. Les administrateurs peuvent gérer la charge de travail teams entière ou ils peuvent avoir des autorisations déléguées pour résoudre les problèmes de qualité des appels ou gérer les besoins téléphoniques de votre organisation.

## <a name="teams-roles-and-capabilities"></a>Rôles et fonctionnalités de Teams

Plusieurs rôles d’administrateur teams sont disponibles : administrateur de service Teams, administrateur des communications Teams, spécialiste du support des communications Teams, ingénieur du support des communications Teams et administrateur de périphériques Teams. Examinez le tableau suivant pour comprendre ce que chaque rôle peut faire et les outils que l’administrateur peut utiliser dans le Centre d’administration Microsoft Teams et PowerShell.

Pour continuer, vous devez être administrateur. Les instructions pour obtenir les autorisations sont dans cet article.

<!-- add Global admin role? -->

| Rôle                                    | Peut effectuer ces tâches                                                           | Peut accéder aux outils suivants                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Administrateur du service Teams             | Gérez le service Teams, gérez et créez des groupes Microsoft 365.        | Tout ce qui se produit dans le Centre d’administration Microsoft Teams et les contrôles PowerShell associés, notamment :<ul><li> Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,3</sup></li><li>Gérez la voix, y compris les stratégies d’appel, l’inventaire des numéros de téléphone et l’affectation. <sup>1</sup></li><li>Gérer la messagerie, y compris les stratégies de messagerie. <sup>1,3</sup></li><li>Gérez tous les paramètres à l’échelle de l’organisation, y compris la fédération, la mise à niveau des équipes et les paramètres du client Teams. <sup>1,3</sup></li><li>Gérez les équipes de l’organisation et leurs paramètres associés, notamment l’appartenance (gestion des groupes prise en charge via PowerShell, gestion des équipes dans le Centre d’administration Teams). <sup>2,3</sup></li><li>Gérez les appareils certifiés Teams et définissez et attribuez des stratégies de configuration. <sup>2</sup></li><li>Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide d’outils de dépannage avancés. <sup>3</sup> </li><li>Accéder à tous les rapports dans le Centre d’administration Microsoft Teams</li><li> Accédez, surveillez et dépannage la qualité et la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. Créez de nouveaux rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels selon vos besoins. Charger et mettre à jour les données de création du CQD.</li><li> [Publier des applications dans le catalogue d’applications client dans le Centre d’administration Microsoft Teams](manage-apps.md)</li></ul> |
| Administrateur des communications Teams      | Gérez les fonctionnalités d’appel et de réunion au sein du service Teams.               | Gérez les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence. <sup>1,3</sup><br><br> Gérez la voix, y compris les stratégies d’appel, l’inventaire des numéros de téléphone et l’affectation. <sup>1</sup><br><br> Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide duet d’outils de dépannage avancés. <sup>3</sup> <br><br> Accédez, surveillez et dépannage de la qualité et de la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. Créez de nouveaux rapports de qualité des appels, mettez à jour et supprimez les rapports de qualité des appels selon vos besoins. Charger et mettre à jour les données de création du CQD.|
| Ingénieur du support technique pour les communications Teams   | Résolution des problèmes de communication au sein de Teams à l’aide **d’outils** avancés. | Affichez la page de profil utilisateur et résolution des problèmes de qualité des appels des utilisateurs à l’aide d’outils de dépannage avancés. <sup>3</sup> <br><br> Accédez, surveillez et dépannage de la qualité et de la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels jusqu’aux utilisateurs qui sont en situation de mauvaise qualité. |
| Spécialiste du support pour les communications Dans Teams | Résolution des problèmes de communication au sein de Teams à l’aide **d’outils de** base.    | Accédez à la page de profil utilisateur pour la résolution des problèmes d’appels dans l’analyse des appels. Peut afficher uniquement les informations de l’utilisateur spécifique recherché.<sup>3</sup> <br><br> Accédez, surveillez et dépannage de la qualité et de la fiabilité des appels des clients à l’aide des données exposées dans le tableau de bord de qualité des appels. |
| Administrateur de périphériques Teams              | Gérez les appareils configurés pour une utilisation avec le service Teams.                    | Gérez la configuration et les mises à jour des appareils, examinez l’état et l’état des périphériques connectés, définissez et appliquez des profils de configuration, et redémarrez des appareils.<p>Le rôle Administrateur de périphériques Teams ne permet pas d’accéder aux données de qualité des appels ou à l’analyse des appels. Pour afficher les données de qualité des appels ou l’analyse des appels, vous devez avoir le rôle Administrateur des communications Teams. |

<sup>1</sup> [PowerShell - Module Skype Entreprise](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - Module Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3 Centre</sup> [d’administration Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they're related to Microsoft 365 Group management>> 
-->
Pour plus d’informations sur les outils d’administration disponibles pour la gestion de Microsoft Teams, voir [Gérer Microsoft Teams.](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)

Pour plus d’informations sur les limites, spécifications et autres exigences qui s’appliquent à Teams, voir Limites et [spécifications pour Microsoft Teams.](limits-specifications-teams.md)

## <a name="assign-users-to-each-role"></a>Attribuer des utilisateurs à chaque rôle

Vous pouvez attribuer ces rôles à des utilisateurs dans Azure AD. Pour découvrir comment attribuer des rôles d’administrateur à un utilisateur dans Azure AD, voir Affecter un utilisateur à des rôles d’administrateur [dans Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles pour chaque rôle

La plupart des outils PowerShell pour ces rôles d’administrateur sont disponibles dans le module Skype Entreprise PowerShell. Il est important de noter que certaines des cmdlets que ces rôles d’administrateur ont accès aux paramètres partagés qui sont également utilisés pour Skype Entreprise Online. Le rôle d’administrateur Skype Entreprise a également accès à toutes les cmdlets dans le module PowerShell de Skype Entreprise.

Pour afficher la liste complète des cmdlets actuellement disponibles pour un rôle donné dans le module Skype Entreprise PowerShell, suivez ces étapes :

1. Attribuez ce rôle à un utilisateur (et assurez-vous qu’il n’a pas d’autres rôles).
2. Connectez-vous au module Skype Entreprise PowerShell :<br>
   a. $session = new-csonlinesession<br>
   b. Import-pssession $session<br>
   c. Utilisez **Get-Module** pour identifier le nom de la session importée (il s’agit d’un nom généré de façon aléatoire).<br>
3. Utilisez **le nom du module Get-Command du** dessus> identifier toutes les  <  cmdlets disponibles

### <a name="related-topics"></a>Sujets associés

- [Vue d’ensemble de Microsoft Teams PowerShell](teams-powershell-overview.md)
- [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

