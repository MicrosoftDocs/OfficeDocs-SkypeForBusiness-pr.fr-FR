---
title: Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/19/2018
ms.topic: article
ms.service: msteams
ms.reviewer: islubin
description: Découvrez comment utiliser les différents rôles d’administration pour gérer les équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 895c0992ea15ebff65ff2e4c5cd47823afc81be1
ms.sourcegitcommit: d4113b46e9afbc4ae6bd3e870851cfb822031ff0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/20/2018
ms.locfileid: "26620074"
---
# <a name="use-microsoft-teams-admin-roles-to-manage-teams"></a>Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams

À l’aide d’Azure Active Directory (AD Azure), vous pouvez désigner les administrateurs qui ont besoin de différents niveaux d’accès pour gérer Microsoft Teams. Les administrateurs peuvent gérer la charge de travail d’équipes entière, ou ils peuvent avez délégué des autorisations pour la résolution des problèmes d’appel des problèmes de qualité ou de la gestion des besoins de téléphonie de votre organisation. 

## <a name="teams-roles-and-capabilities"></a>Rôles d’équipes et fonctionnalités

Il existe quatre rôles d’administrateur équipes : administrateur de service d’équipes, administrateur de communications d’équipes, spécialiste des équipes communications prise en charge et communications équipes ingénieur de support. Consultez le tableau suivant pour comprendre ce que chaque rôle peut faire et choix des outils de l’administrateur peut utiliser les équipes Skype pour Business Admin Center et PowerShell.

<!-- add Global admin role? -->

| Rôle | Peuvent effectuer ces tâches | Les outils suivants peuvent accéder à |
|----- | ------------------ | ------------------------------ |
| Administrateur du service Teams | Gérer le service Microsoft Teams, gérer et créer des groupes Office 365 | Tous les éléments dans le Microsoft Teams & Skype pour Business Admin Center et contrôles PowerShell associés, notamment :<br><br> Gérer des réunions, y compris des réunions de conférence, les configurations et les stratégies de ponts<sup>1,3</sup><br><br> Gérer la voix, notamment l’appel de stratégies et téléphone inventaire et affectation numéro<sup>1</sup><br><br> Gérer la messagerie, y compris la messagerie stratégies<sup>1,3</sup><br><br> Gérer tous les paramètres à l’échelle de l’organisation, y compris la fédération, la mise à niveau des équipes et équipes client paramètres<sup>1,3</sup><br><br> Gérer les équipes dans l’organisation et leurs paramètres associés, y compris l’appartenance (gestion de groupe prises en charge par le biais de PowerShell, gestion de l’équipe dans le portail d’administration présentant) <sup>23</sup><br><br> Afficher la page de profil utilisateur et de résoudre les problèmes de qualité des appels utilisateur à l’aide de diagnostic<sup>3</sup> dépannage avancé |
| Administrateur des communications Teams | Gérer les fonctionnalités d’appels et de réunions au sein du service Microsoft Teams | Gérer des réunions, y compris des réunions de conférence, les configurations et les stratégies de ponts<sup>1,3</sup><br><br> Gérer la voix, notamment l’appel de stratégies et téléphone inventaire et affectation numéro<sup>1</sup><br><br> Afficher la page de profil utilisateur et de résoudre les problèmes de qualité des appels utilisateur à l’aide de diagnostic<sup>1,3</sup> dépannage avancé |
| Ingénieur du support technique pour les communications Teams | Résoudre les problèmes de communication au sein des équipes à l’aide des outils **avancés** . | Accès à la page de profil utilisateur pour résoudre les problèmes des appels dans Analytique d’appel. Afficher les informations enregistrement appel complète. <sup>3</sup> |
| Spécialiste des équipes Communications prise en charge | Résoudre les problèmes de communication au sein des équipes à l’aide des outils de **base** .| Accès à la page de profil utilisateur pour résoudre les problèmes des appels dans Analytique d’appel. Peut afficher uniquement les informations de l’utilisateur spécifique recherché.<sup>3</sup>

<sup>1</sup> [PowerShell - Skype pour le module d’entreprise](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)<br>
<sup>2</sup> [PowerShell - module équipes Microsoft](https://www.powershellgallery.com/packages/MicrosoftTeams/)<br>
<sup>3</sup> [les équipes Microsoft et Skype entreprise centre d’administration](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)
<!-- <sup>4</sup> Azure Active Directory Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
<sup>5</sup> Microsoft 365 Admin Center <<note that these are going to come later because they’re related to O365 Group management>> 
-->
Pour plus d’informations sur les outils d’administration disponibles pour la gestion de Microsoft Teams, voir [Gestion des équipes Microsoft](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center).

## <a name="assign-users-to-each-role"></a>Affecter des utilisateurs à chaque rôle

Vous pouvez affecter des utilisateurs à ces rôles dans Azure Active Directory. Pour savoir comment attribuer des rôles administratifs à un utilisateur dans Azure Active Directory, consultez la rubrique [affecter un utilisateur à des rôles d’administrateur dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

## <a name="cmdlets-available-for-each-role"></a>Applets de commande disponibles pour chaque rôle.

La plupart des outils de PowerShell pour ces rôles d’administrateur live dans le Skype pour le module PowerShell Business, et il est important de noter que certaines des applets de commande que ces rôles d’administration ont accès au contrôle partagés paramètres qui sont également exploitées pour Skype pour Business Online. Pour afficher la liste complète des applets de commande actuellement disponibles pour un rôle donné dans la Skype pour le module PowerShell Business, procédez comme suit :

1. Attribuer ce rôle à un utilisateur (et assurez-vous ne qu’aucun autre rôle de l’utilisateur).
2. Se connecter à la Skype pour le module PowerShell d’entreprise :<br>
   a. $session = nouveau csonlinesession<br>
   b. Import-pssession $session<br>
   c. Utilisez **Get-Module** pour identifier le nom de la session importé (il s’agira d’un nom généré de manière aléatoire).<br>
3. Utilisez **Get-Command - Module** <*nom à partir du haut*> pour identifier toutes les applets de commande disponibles

### <a name="related-topics"></a>Rubriques connexes

- [Vue d’ensemble d’équipes Microsoft PowerShell](teams-powershell-overview.md)
- [Les équipes Microsoft PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
- [Affecter des propriétaires de l’équipe et des membres dans Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-roles-permissions)

