---
title: Utiliser les rôles d’administrateur de Microsoft teams pour gérer teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.errorpage.needadminpermsforadmincenter.assignadminrolesarticle
- ms.teamsadmincenter.errorpage.needadminperms.assignadminrolesarticle
- ms.teamsadmincenter.signin.error.nopermissions
- ms.teamsadmincenter.directrouting.cqd
ms.reviewer: islubin
description: Apprenez à utiliser les différents rôles d’administration pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97288109f7998a8d29520169e229a5546da94bc5
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2019
ms.locfileid: "37616056"
---
# <a name="use-microsoft-teams-administrator-roles-to-manage-teams"></a>Utiliser les rôles d’administrateur de Microsoft teams pour gérer teams

À l’aide d’Azure Active Directory (Azure AD), vous pouvez désigner les administrateurs qui ont besoin d’un niveau d’accès différent pour gérer Microsoft Teams. Les administrateurs peuvent gérer toute la charge de travail teams ou disposer d’autorisations déléguées pour la résolution des problèmes de qualité des appels ou la gestion des besoins en téléphonie de votre organisation. 

## <a name="teams-roles-and-capabilities"></a>Rôles et capacités de teams

Il existe quatre rôles d’administrateur d’équipes disponibles : l’administrateur de service Teams, l’administrateur des communications Teams, le support technique de Microsoft Team communications et l’ingénieur du support des communications Teams. Consultez le tableau ci-dessous pour comprendre le fonctionnement de chaque rôle et les outils qu’il peut utiliser dans le centre d’administration Microsoft teams et PowerShell.



<!-- add Global admin role? -->

| Rôle | Tâches possibles | Peut accéder aux outils suivants |
|----- | ------------------ | ------------------------------ |
| Administrateur du service Teams | Gérer le service équipes et gérer et créer des groupes Office 365 | Tout le centre d’administration Microsoft teams et les contrôles PowerShell associés, notamment :<ul><li> Gestion des réunions, y compris des stratégies de réunion, des configurations et des ponts de conférence. <sup>1, 3</sup></li><li>Gérer la voix, y compris les politiques d’appel et le numéro de téléphone et l’affectation. <sup>1</sup></li><li>Gérer les messages, y compris les stratégies de messagerie. <sup>1, 3</sup></li><li>Gestion de tous les paramètres à l’échelle de l’organisation, y compris les paramètres de Fédération, de mise à niveau des équipes et du client Teams. s<sup>1, 3</sup></li><li>Gérer les équipes au sein de l’organisation et leurs paramètres associés, y compris l’appartenance (gestion des groupes prises en charge par PowerShell, gestion des équipes dans le centre d’administration Teams). <sup>23</sup></li><li>Afficher la page de profil de l’utilisateur et résoudre les problèmes de qualité des appels d’utilisateur à l’aide du jeu d’outils avancé. <sup>3</sup> </li><li> Accédez à des données exposées dans le tableau de bord de qualité des appels pour surveiller et résoudre les problèmes de qualité des appels et de la fiabilité du client à l’aide des données exposées dans le tableau de bord de qualité d’appel (bord). Créer des rapports, mettre à jour et supprimer des rapports selon vos besoins. Téléchargez et mettez à jour les données de bâtiment bord.</li><li> [Publier des applications dans le catalogue d’applications client à partir du client teams](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)</li></ul> |
| Administrateur des communications Teams | Gérer les fonctionnalités d’appel et de réunion à l’aide du service Teams. | Gestion des réunions, y compris des stratégies de réunion, des configurations et des ponts de conférence. <sup>1, 3</sup><br><br> Gérer la voix, y compris les politiques d’appel et le numéro de téléphone et l’affectation. <sup>1</sup><br><br> Afficher la page de profil de l’utilisateur et résoudre les problèmes de qualité des appels d’utilisateur à l’aide du jeu d’outils avancé de dépannage. <sup>3</sup> <br><br> Accédez à des données exposées dans le tableau de bord de qualité des appels pour surveiller et résoudre les problèmes de qualité des appels et de la fiabilité du client à l’aide des données exposées dans le tableau de bord de qualité d’appel (bord). Créer des rapports, mettre à jour et supprimer des rapports selon vos besoins. Téléchargez et mettez à jour les données de bâtiment bord.|
| Ingénieur du support technique pour les communications Teams | Résoudre les problèmes de communication dans teams à l’aide des outils **avancés** . | Afficher la page de profil de l’utilisateur et résoudre les problèmes de qualité des appels d’utilisateur à l’aide du jeu d’outils avancé. <sup>3</sup> <br><br> Accédez à des données exposées dans le tableau de bord de qualité des appels pour surveiller et résoudre les problèmes de qualité des appels et de la fiabilité du client à l’aide des données exposées dans le tableau de bord de qualité d’appel (bord). |
| Spécialiste du support des communications teams | Résoudre les problèmes de communication dans teams à l’aide d’outils de **base** .| Page de profil utilisateur Access pour la résolution des problèmes d’analyse des appels. Peut afficher uniquement les informations de l’utilisateur spécifique recherché.<sup>3</sup> <br><br> Accédez à des données exposées dans le tableau de bord de qualité des appels pour surveiller et résoudre les problèmes de qualité des appels et de la fiabilité du client.  

<sup>1</sup> [PowerShell-module Skype entreprise](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell-module Microsoft teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [Centre d’administration Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory admin center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Pour plus d’informations sur les outils d’administration disponibles pour la gestion de Microsoft Teams, reportez-vous à [gestion de Microsoft teams](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

Pour plus d’informations sur les limites et les spécifications, ainsi que d’autres conditions qui s’appliquent aux équipes, voir [limites et caractéristiques de Microsoft teams](limits-specifications-teams.md).

## <a name="assign-users-to-each-role"></a>Attribuer des utilisateurs à chaque rôle

Vous pouvez attribuer des utilisateurs à ces rôles dans Azure AD. Pour plus d’informations sur l’attribution de rôles d’administrateur à un utilisateur dans Azure AD, voir [affecter des rôles d’administrateur dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Cmdlets disponibles pour chaque rôle

La plupart des outils PowerShell pour ces rôles d’administrateur résident dans le module PowerShell de Skype entreprise, et il est important de noter que certaines des applets de commande dont ces rôles d’administrateur ont accès à des paramètres partagés qui sont également utilisés pour Skype entreprise online. Le rôle d’administrateur Skype entreprise a également accès à toutes les applets de la fonction du module PowerShell Skype entreprise.

Pour afficher la liste complète des cmdlets actuellement disponibles pour un rôle donné dans le module PowerShell Skype entreprise, procédez comme suit :

1. Attribuez ce rôle à un utilisateur (et assurez-vous que l’utilisateur n’a pas d’autres rôles).
2. Connectez-vous au module PowerShell Skype entreprise :<br>
   a. $session = New-csonlinesession<br>
   b. Importation-PowerShell $session<br>
   c. Utilisez **Get-Module** pour identifier le nom de la session importée (le nom sera généré de manière aléatoire).<br>
3. Utiliser **Get-Command-** <*nom du module ci-dessus*> pour identifier toutes les applets de commande disponibles

### <a name="related-topics"></a>Voir aussi

- [Vue d’ensemble de Microsoft teams PowerShell](teams-powershell-overview.md)
- [Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Affecter des propriétaires d’équipe et des membres dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

