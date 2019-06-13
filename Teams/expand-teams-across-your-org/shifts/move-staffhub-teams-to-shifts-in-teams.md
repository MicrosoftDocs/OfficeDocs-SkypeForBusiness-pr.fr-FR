---
title: Déplacer vos équipes de StaffHub vers Shifts dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données vers Shifts dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780808"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Faire passer vos équipes de Microsoft StaffHub vers Shifts dans Microsoft Teams

> [!IMPORTANT]
> Microsoft StaffHub sera retiré le 1er octobre 2019. Nous développons les fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, Teams inclut l’application Shifts pour la gestion de la planification et des fonctionnalités supplémentaires seront déployées à l’avenir. StaffHub cessera de fonctionner pour tous les utilisateurs le 1er octobre 2019. Toute personne qui essaie d’ouvrir StaffHub verra s’afficher un message lui permettant de télécharger Teams. Pour en savoir plus, consultez l’article [Retrait de Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).

L’application Shifts dans Teams offre une approche simple pour gérer les plannings et le flux constant des échanges et des annulations de planning qui se produisent quotidiennement. Les membres d’une équipe peuvent accéder à leurs informations de planification et de services directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leurs plannings et demander des congés.

Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier des données de Shifts dans Teams. Cela couvre les sujets suivants :

- [Ce que vous devez savoir sur la migration vers Teams](#what-you-need-to-know-about-the-move-to-teams)
- [Préparation](#prepare)
- [Organiser un projet pilote](#conduct-a-pilot) 
- [Aller au-delà de votre pilote et déplacer toutes les équipes StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Surveiller l’utilisation de Teams](#monitor-teams-usage)
- [Résolution des problèmes](#troubleshooting)

Que vous travailliez dans une petite entreprise avec une ou deux équipes StaffHub ou une grande entreprise disposant de centaines d’équipes StaffHub, vous trouverez ici les conseils d’administration nécessaires pour améliorer la transition vers Teams.

Vous devez être un administrateur général pour effectuer les étapes décrites dans cet article. Si vous ne l’avez pas déjà fait, consultez le [forum aux questions sur le retrait StaffHub](microsoft-staffhub-to-be-retired.md)pour obtenir des réponses aux questions que vous vous posez.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Ce que vous devez savoir sur la migration vers Teams

### <a name="when-to-move-to-teams"></a>Quand déplacer vers Teams ?

StaffHub sera retiré le 1er octobre 2019. Nous vous encourageons à commencer à utiliser Teams aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub. Avec la gestion des planifications comme la fonctionnalité la plus fréquemment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans Teams pour continuer.

### <a name="what-is-moved-to-teams"></a>Ce qui est déplacé vers Teams

Les détails de l’utilisateur, les informations de calendrier, les conversations et les données de fichier sont transférés vers Teams. Cela inclut les membres de l’équipe, les plannings d’équipe, les conversations et les fichiers des 90 derniers jours.

Chaque équipe StaffHub a besoin d’un groupe Office 365 correspondant. Si une équipe StaffHub ne possède pas de groupe Office 365 associé, un groupe Office est automatiquement créé pour vous permettre de prendre en charge la transition. Étant donné la différence entre les noms d’équipes et les noms des groupes entre Teams et StaffHub, vous risquez d’avoir un nom d’équipe différent dans Teams.

Au fur et à mesure que vous transférez des équipes de StaffHub à Teams, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers Shifts dans Teams. Nous vous recommandons de communiquer ce changement au sein de votre organisation pour minimiser les perturbations et encourager les utilisateurs à adopter et explorer Teams. Si vous avez Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs StaffHub au sein de votre organisation qui ont besoin d’en savoir plus sur cette modification.  

Il n’existe pas d’option de restauration une fois que vous avez déplacé une équipe StaffHub vers Teams.

### <a name="user-experience-when-you-move-a-team"></a>Expérience utilisateur lorsque vous déplacez une équipe

Il y a peu de temps d’arrêt (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leurs équipes passent de StaffHub à Shifts dans Teams. Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que la migration vers Teams soit terminée. Une fois le déplacement terminé, les membres de l’équipe voient s’afficher un message leur indiquant qu’ils doivent commencer à utiliser Shifts dans Teams pour accéder à leur planning d’équipe. Voici un exemple de message que les utilisateurs voient dans StaffHub une fois l’équipe StaffHub déplacée vers Teams.

![Exemple de message que voient les utilisateurs.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Voici un exemple de message que les utilisateurs voient dans StaffHub une fois l’équipe StaffHub déplacée vers Teams")

## <a name="prepare"></a>Préparer

Pour préparer la migration vers Teams, procédez comme suit.

### <a name="check-that-prerequisites-are-met"></a>Vérifier que les conditions préalables sont remplies

Avant de transférer une équipe StaffHub à Teams, assurez-vous que :

- L’utilisateur connecté est un administrateur général.
- Teams est activé pour tous les utilisateurs du client.
- La création de groupes Office 365 est activée dans le client.
- Le teamId StaffHub est valide.
- L’équipe StaffHub contient des membres. 
- Tous les membres de l’équipe StaffHub sont liés à un compte Azure AD. 

Si ces conditions préalables ne sont pas remplies, la demande de déplacement échouera. 

### <a name="assign-teams-licenses"></a>Assigner des licences Teams

Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et une licence de Teams doit lui être attribuée. L’attribution d’une licence Teams permet aux utilisateurs d’accéder à Teams.

Vous gérez les licences de Teams dans le centre d’administration Microsoft 365. Pour en savoir plus, reportez-vous à la rubrique [Gestion de l'accès des utilisateurs à Microsoft Teams](../../user-access.md).

> [!NOTE]
> Si votre organisation utilise Skype Entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer Teams pour vos employés de terrain qui peuvent alors exécuter Teams en parallèle de Skype Entreprise. Avec ce mode de coexistence, intitulé*Islands*, chaque application cliente fonctionne comme une solution distincte. Pour en savoir plus, lisez la rubrique [Comprendre la coexistence et l’interopérabilité de Teams et Skype Entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

Si vous ne l’avez pas encore fait,[Installer le module PowerShell StaffHub](install-the-staffhub-powershell-module.md). 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Configurer des comptes pour les utilisateurs de StaffHub qui n’ont pas d’identité dans Azure AD

Chaque responsable et membre de l’équipe doivent avoir une identité dans Azure Active Directory (Azure AD). Si un utilisateur n’a pas encore d’identité dans Azure AD, configurez un compte pour lui. Voici comment procéder. 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>Obtenir la liste de tous les utilisateurs d’équipes StaffHub qui ont des membres d’équipe qui n’ont pas été configurés avec un compte Azure AD

Exécutez la commande suivante :
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>Configuration du compte

Effectuez l’une des actions suivantes :

- Convertissez le compte et liez-le à un compte configuré.

  Les propriétaires et responsables d’équipes StaffHub peuvent convertir un compte factice ou inactif et le lier à un compte configuré dans StaffHub en remplaçant l’adresse de messagerie de l’utilisateur par un nom d’utilisateur principal valide dans la page Paramètres d’équipe StaffHub.

- Supprimez le compte non configuré, puis rajoutez-le à l’aide du nom d’utilisateur principal.
    1. Exécutez l'applet de commande [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer le compte non approvisionné de l’équipe StaffHub.
    2. Exécutez l'applet de commande[Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) pour rajouter le compte à l’équipe StaffHub à l’aide du nom d’utilisateur principal. 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Attribuer la stratégie de configuration de l’application FirstlineWorker aux utilisateurs

Teams inclut une stratégie de configuration d’application FirstlineWorker intégrée que vous pouvez utiliser pour personnaliser Teams afin de mettre en évidence les applications les plus importantes pour les employés terrain de votre organisation. Lorsque vous affectez cette stratégie à des utilisateurs, les applications de la stratégie sont épinglées à la barre de l’application dans Teams pour un accès rapide et facile. Les autres applications ajoutées à Teams sont accessibles dans la barre d’application en cliquant sur **... Autres applications** sur le bureau Teams et les clients Web et en balayant vers le haut dans le client mobile Teams. Par défaut, la stratégie de configuration de l’application FirstlineWorker inclut les applications Activité, Shifts, Chat et Appels.

Pour connaître la procédure d’affectation de la stratégie de configuration de l’application FirstlineWorker aux utilisateurs, voir [utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler Shifts à Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Une fois que vous avez affecté une stratégie, la prise en compte peut prendre jusqu’à 24 heures.

Nous vous recommandons d’effectuer cette étape au moins une semaine avant de déplacer vos équipes StaffHub et vos utilisateurs vers Teams. Lorsque les utilisateurs sont membres de Teams, assurez-vous qu’ils peuvent voir et accéder à l’application Shifts.

Vous pouvez également créer des stratégies de configuration d’applications personnalisées et modifier les paramètres dans la stratégie d’installation globale de l’application. Pour en savoir plus, voir [gérer les stratégies de configuration des applications dans Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Intégrer des utilisateurs à Teams

Dans le cadre de votre stratégie d’intégration, fournissez des formations et des instructions aux utilisateurs pour leur permettre de se familiariser avec Teams. N’oubliez pas d’inclure les ressources suivantes pour qu’ils sachent où obtenir des clients Teams, les formations et le support :

- [Client Web Teams](https://teams.microsoft.com)
- [Liens de téléchargement du client de bureau et mobile](https://teams.microsoft.com/downloads)
- [Vidéos de formation Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentation d'aide Teams](https://support.office.com/teams)

Pour obtenir des instructions sur le déploiement de Teams et la conduite de l’adoption de Teams, voir comment[déployer Teams](../../How-to-roll-out-teams.md) et [adopter Teams](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Mener un projet pilote

Nous vous recommandons de commencer par déplacer deux ou trois équipes StaffHub pour un groupe sélectionné d’adoptions précoces. L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams. Il permet également d’identifier les champions qui peuvent favoriser l’adoption au sein de votre organisation. Si vous êtes une petite entreprise qui n’a pas besoin d’une approche progressive, il se peut que tout ce que vous avez besoin de faire est effectuer la procédure décrite dans cette section pour passer de StaffHub à Teams.

### <a name="identify-pilot-teams"></a>Identification des équipes pilotes

Renseignez-vous sur l’identification de deux ou trois équipes pilotes. Tous les membres de l’équipe doivent s’engager à utiliser Shifts dans Teams pour gérer leurs plannings et communiquer et collaborer ensemble.

### <a name="identify-team-champions"></a>Identifier les champions d’équipe

Identifiez les champions au sein des équipes pilotes et encadrez-les pour favoriser la promotion de Shifts. Les champions d’équipe sont passionnés par ce qu’ils font, partageant leurs propres apprentissages pour offrir un support et des conseils aux membres de l’équipe. Les champions d’équipe peuvent être des responsables d’équipe ou des gestionnaires.

Les champions d’équipe doivent s’assurer que les membres de l’équipe sont configurés en leur permettant d’[obtenir des clients Teams](../../get-clients.md), de se connecter à Teams et de consulter leur planning dans Shifts, et de commencer à discuter. Les utilisateurs qui connaissent déjà StaffHub seront opérationnels rapidement dans Shifts. Vous pouvez également les diriger vers [l’aide Shifts](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) pour obtenir de l’aide supplémentaire.

### <a name="move-a-staffhub-team"></a>Déplacer une équipe StaffHub

Pour déplacer une équipe StaffHub à la fois, procédez comme suit. Nous vous recommandons d’utiliser cette approche pour vos équipes pilotes. Plus tard, lorsque vous serez prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes StaffHub](#move-your-staffhub-teams) pour connaître la procédure de déplacement de plusieurs équipes à la fois.

Exécutez la commande suivante pour déplacer une équipe StaffHub.

```
Move-StaffHubTeam -TeamId <String>
```
Exemple :

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Voici un exemple de réponse que vous obtenez lorsque vous envoyez une demande de déplacement d’une équipe StaffHub vers Teams.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Procédez comme suit pour vérifier l’état de vos demandes de déplacement.

```
Get-TeamMigrationJobStatus <String>
```
Exemple :

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Déplacer des fichiers d’une équipe StaffHub vers Teams

Cette étape s’applique uniquement si l’équipe StaffHub que vous avez déplacée vers Teams a des fichiers que vous voulez déplacer également vers Teams. Vous pouvez déplacer des fichiers directement dans SharePoint Online ou à l’aide de PowerShell. 

#### <a name="in-sharepoint-online"></a>Dans SharePoint Online

Découvrez [comment déplacer des fichiers dans SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Utiliser PowerShell

Téléchargez et installez le fichier [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588) si ce n’est pas déjà fait. Il contient les applets de commande dont vous avez besoin pour déplacer des fichiers.  

Utilisez l'applet de commande [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)pour vous connecter au site d’équipe SharePoint Online.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Pour chaque fichier que vous voulez déplacer de StaffHub à Teams, utilisez l'applet de commande [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile)pour déplacer le fichier.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Pour déplacer plusieurs fichiers, parcourez les fichiers et exécutez la deuxième commande sur la boucle. Vous n’avez pas besoin de répéter la première commande si la session reste active.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Aller au-delà de votre pilote et déplacer toutes les équipes StaffHub

### <a name="raise-awareness"></a>Sensibilisation

Lorsque vous êtes prêt à aller au-delà de vos équipes pilotes et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important de commencer par communiquer la modification au sein de votre organisation. Diffusez la nouvelle sur Shifts et la transition vers Teams afin de sensibiliser les membres, de susciter l’enthousiasme et d’adopter l’adoption.

### <a name="move-your-staffhub-teams"></a>Déplacer vos équipes StaffHub

Pour déplacer toutes les équipes StaffHub en même temps, procédez comme suit. Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques. Si vous voulez déplacer StaffHub équipes l’une après l’autre, voir [déplacer une équipe StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Déplacer toutes vos équipes StaffHub

Exécutez la commande suivante pour obtenir la liste de toutes les équipes StaffHub au sein de votre organisation.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Voici un exemple de la réponse.

Pour les équipes qui ont déjà été déplacées vers Teams ou qui existent déjà dans Teams, le jobId est «nul», car il n’est pas nécessaire d’effectuer une tâches pour déplacer l’équipe.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Déplacer des équipes StaffHub spécifiques

Exécutez la commande suivante pour obtenir la liste de tous les ID d’équipes StaffHub au sein de votre organisation.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Dans les résultats renvoyés par `Get-StaffHubteamsForTenant` l’applet de commande que vous avez exécutée précédemment, sélectionnez les ID d’équipe que vous voulez déplacer, puis ajoutez-les à un fichier CSV (valeurs séparées par des virgules).

Voici un exemple de mise en forme du fichier CSV.

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Une fois que vous avez créé le fichier CSV, exécutez la commande suivante pour déplacer les équipes que vous avez spécifiées dans le fichier CSV.

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Vérifier que vos équipes StaffHub ont été déplacées vers Teams

Exécutez la commande suivante pour obtenir la liste de toutes les équipes Shifts au sein de votre organisation. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Déplacer des fichiers de vos équipes StaffHub vers Teams

Si les équipes StaffHub que vous avez déplacées contiennent des fichiers que vous voulez déplacer vers Teams, voir [déplacer des fichiers d’une équipe StaffHub vers Teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Surveiller l’utilisation de Teams

Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous donne la perspective nécessaire pour savoir où hiérarchiser les efforts de formation et de communication dans votre entreprise. Étant donné que Shifts est une application dans Teams, vous pouvez afficher l’utilisation via les rapports de Teams. Pour plus d’informations, voir[Création de rapports Teams dans le Centre d’administration Microsoft Teams](../../teams-analytics-and-reports/teams-reporting-reference.md)et[Rapports sur l’activité de Teams dans le Centre d’administration Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Résolution des problèmes 

**Lorsque vous tentez de déplacer des fichiers de StaffHub à Teams, un message d’erreur «autorisation refusée» s’affiche.**

Cela peut se produire si vous essayez de déplacer des fichiers dans un groupe Office 365 privé dont vous n’êtes pas membre. Si c’est le cas, utilisez l'applet de commande [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) pour vous ajouter à l’équipe StaffHub, puis déplacez les fichiers. Une fois les fichiers déplacés, utilisez l’applet de commande [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember)pour vous supprimer de l’équipe. 

**Lorsque vous essayez de déplacer des fichiers de StaffHub à Teams, un message d’erreur indique que le dossier général n’existe pas.**

Exécutez la commande suivante pour ajouter le dossier général à SharePoint, puis réessayez :

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Rubriques connexes
- [Comment déployer Microsoft Teams](../../How-to-roll-out-teams.md)
- [Fin de parcours pour Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Gérer l’application Shifts pour votre organisation dans Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Référence PowerShell StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
