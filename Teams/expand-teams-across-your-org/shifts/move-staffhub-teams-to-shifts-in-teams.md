---
title: Déplacer vos équipes de Microsoft StaffHub vers Shifts dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données en équipes dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9468dea64c464b3bfc2f0cec7c53f46e2f388c1f
ms.sourcegitcommit: 7d5dd650480ca2e55c24ce30408a5058067f6932
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37775083"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Déplacer vos équipes Microsoft StaffHub vers des équipes dans Microsoft teams

> [!IMPORTANT]
> À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).

L’application Shifts dans teams fournit une méthode simple pour gérer les plannings et le flux constant de permutations et d’annulations de Shift qui se produisent quotidiennement. Les membres d’une équipe peuvent accéder à leur planning et leur transférer directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leur planning et demander un congé.

Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier vos données en vue de leur déplacement dans Teams. Ce service comprend les éléments suivants :

- [Ce que vous devez savoir sur le déplacement dans teams](#what-you-need-to-know-about-the-move-to-teams)
- [Prévenir](#prepare)
- [Conduire une pilote](#conduct-a-pilot) 
- [Aller au-delà de votre pilote et déplacer toutes les équipes de StaffHub](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Surveiller l’utilisation des équipes](#monitor-teams-usage)
- [Résolution des problèmes](#troubleshooting)

Que vous soyez une petite entreprise disposant d’une ou de deux équipes StaffHub ou d’une grande entreprise ayant des centaines d’équipes, vous trouverez ci-dessous les conseils d’administration dont vous avez besoin pour faciliter la transition vers les équipes.

Pour pouvoir effectuer les étapes décrites dans cet article, vous devez être un administrateur général. Si vous ne l’avez pas déjà fait, consultez le [Forum aux questions de retraite StaffHub](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses aux questions que vous pourriez rencontrer.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Ce que vous devez savoir sur le déplacement dans teams

### <a name="when-to-move-to-teams"></a>Quand déplacer vers teams

À compter du 31 décembre 2019, StaffHub sera supprimé. Nous vous encourageons à commencer à utiliser teams dès aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub. Avec la gestion des plannings étant la fonctionnalité la plus couramment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans les équipes qui progressent.

### <a name="what-is-moved-to-teams"></a>Ce qui est déplacé vers teams

Lorsque vous déplacez une équipe StaffHub, l’appartenance à une équipe, les détails de l’utilisateur, les planifications d’équipe et les données de conversation sont déplacées vers Teams. Les fichiers ne sont pas déplacés lorsque vous déplacez une équipe StaffHub. S’il s’agit d’une équipe StaffHub qui contient les fichiers que vous voulez déplacer vers Teams, vous pouvez déplacer les fichiers dans une autre étape.

Chaque équipe StaffHub doit avoir un groupe Office 365 correspondant. Si une équipe StaffHub est associée à un groupe Office 365, le paramètre de confidentialité du groupe est conservé lorsque vous déplacez l’équipe. Si une équipe StaffHub n’a pas de groupe Office 365 associé, un groupe avec un paramètre de confidentialité de privé est créé automatiquement pour que vous la prennez en charge.  En raison de la différence entre les noms d’équipe et de groupe entre teams et StaffHub, il est possible que vous voyiez un nom d’équipe différent dans Teams. 

Lorsque vous transformez des équipes de StaffHub en équipes, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers des équipes dans Teams. Nous vous recommandons de communiquer ce changement au sein de votre organisation afin de limiter les perturbations et d’encourager les utilisateurs à adopter et à explorer les équipes. Si vous disposez d’Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs de StaffHub de votre organisation qui doivent savoir ce changement.  

Il n’existe aucune option de restauration après le déplacement d’une équipe StaffHub vers Teams.

### <a name="user-experience-when-you-move-a-team"></a>Utilisation de l’interface utilisateur lorsque vous déplacez une équipe

Il y a un minimum d’interruption de service (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leur équipe passe de StaffHub à équipes. Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que le passage aux équipes soit terminé. Lorsque le déplacement est terminé, les membres de l’équipe voient s’afficher un message lui informant qu’ils doivent commencer par utiliser les Shifts dans teams pour accéder à leur planning d’équipe. Voici un exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub a été déplacée vers Teams.

![Exemple du message que les utilisateurs voient.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemple du message que les utilisateurs voient dans StaffHub après le déplacement de l’équipe StaffHub vers teams")

## <a name="prepare"></a>Prévenir

Voici comment préparer le déplacement vers Teams.

### <a name="check-that-prerequisites-are-met"></a>Vérifier que les conditions préalables sont remplies

Avant de déplacer une équipe StaffHub vers Teams, assurez-vous que :

- L’utilisateur connecté est un administrateur global.
- Équipes est activée pour tous les utilisateurs du client.
- La création de groupes Office 365 est activée dans le client.
- StaffHub teamId est valide.
- L’équipe StaffHub possède au moins un propriétaire d’équipe.
- L’équipe StaffHub contient les membres.
- Tous les membres de l’équipe StaffHub sont liés à un compte Azure AD.
- Tous les membres de l’équipe StaffHub disposent d’une licence Teams.  

Si ces éléments requis n’ont pas été satisfaits, la demande de déplacement échoue.

### <a name="assign-teams-licenses"></a>Assigner des licences Teams

Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et être disposant d’une licence d’équipe. L’attribution d’une licence d’équipe aux utilisateurs leur permet d’accéder à Teams.

Pour gérer les licences d’équipe, vous devez utiliser le centre d’administration 365 Microsoft. Pour en savoir plus, voir [gérer l’accès des utilisateurs aux équipes](../../user-access.md).

> [!NOTE]
> Si votre organisation utilise Skype entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer les équipes pour vos travailleurs terrain qui peuvent alors exécuter des équipes en même temps que Skype entreprise. Dans ce mode de coexistence, intitulé *îlots*, chaque application cliente fonctionne en tant que solution distincte. Pour en savoir plus, reportez-vous à la rubrique [Présentation des équipes et coexistence et interopérabilité de Skype entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>Installez la version préliminaire du module PowerShell StaffHub

Si ce n’est déjà fait, [Installez la version préliminaire du module PowerShell StaffHub](install-the-staffhub-powershell-module.md).

Vous devez avoir installé la version préliminaire du module pour déplacer vos équipes StaffHub vers Teams.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>Créer un lien vers un compte Azure AD pour les membres de l’équipe StaffHub qui n’en ont pas

Chaque membre de l’équipe StaffHub doit être lié à un compte Azure Active Directory (Azure AD). Les utilisateurs de votre organisation ne seront pas associés à un compte Azure AD si l’un des scénarios suivants s’appliquent :

- Un propriétaire d’équipe a ajouté un utilisateur qui ne possède pas de compte Azure AD.
- Un propriétaire d’équipe a invité un utilisateur à une équipe StaffHub et ce dernier n’a pas accepté l’invitation.

Ces utilisateurs ont des comptes inactifs et indiquent l’état d’utilisateur inconnu, invité ou InviteRejected. Vous pouvez lier un compte Azure AD pour ces utilisateurs.  Voici comment procéder.

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>Obtenir la liste de tous les comptes inactifs dans StaffHub teams

Pour obtenir la liste de tous les comptes inactifs dans StaffHub Teams, exécutez les commandes suivantes, puis exportez la liste dans un fichier CSV. Chaque commande doit être exécutée séparément.

```
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>Lier le compte

Effectuez l’une des actions suivantes :

- Conversion et liaison du compte.

  Les propriétaires d’équipes et responsables de StaffHub peuvent convertir un compte inactif et le lier à un compte Azure AD dans StaffHub en définissant l’adresse de courrier de l’utilisateur sur un UPN valide dans la page Paramètres de l’équipe StaffHub.

- Supprimez le compte non lié, puis rajoutez-le à l’aide du nom d’utilisateur principal.
    1. Exécutez l’applet de passe [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) pour supprimer le compte non approvisionné de l’équipe StaffHub.
    2. Exécutez l’applet de passe [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) pour ajouter le compte à l’équipe StaffHub à l’aide du nom d’utilisateur principal.

- Supprimez le compte inactif. Utilisez cette option si le compte d’utilisateur n’est plus nécessaire.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs

Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez utiliser pour personnaliser teams afin de mettre en évidence les applications les plus importantes pour les travailleurs terrain au sein de votre organisation. Lorsque vous attribuez ce paramètre de stratégie aux utilisateurs, les applications de la stratégie sont épinglées à la barre de l’application dans teams pour un accès rapide et facile. Les autres applications ajoutées aux équipes sont accessibles dans la barre de l’application en cliquant sur **... D’autres applications** sont installées sur les clients de bureau et Web teams en effectuant un balayage vers le haut dans le client Microsoft teams mobile. Par défaut, la stratégie de configuration de l’application FirstlineWorker comprend les applications activité, équipes, discussions et appels.

Pour plus d’informations sur l’affectation de la stratégie de configuration de l’application FirstlineWorker aux utilisateurs, voir [utilisation de la stratégie de configuration des applications FirstlineWorker pour épingler des équipes à des équipes](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Dès lors que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire.

Nous vous recommandons de terminer cette étape au moins une semaine avant de déplacer vos équipes et utilisateurs StaffHub vers Teams. Lorsque les utilisateurs sont sur Teams, assurez-vous qu’ils peuvent afficher l’application Shifts et y accéder.

Vous pouvez également créer des stratégies de configuration d’applications personnalisées et modifier les paramètres de la stratégie de configuration de l’application globale. Pour en savoir plus, consultez [gérer les stratégies de configuration des applications dans Microsoft teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Utilisateurs intégrés à teams

Dans le cadre de votre stratégie d’intégration, vous pouvez fournir des formations et des conseils pour permettre aux utilisateurs de se familiariser avec Teams. Partagez les ressources suivantes avec des utilisateurs afin qu’ils sachent où sont les clients Teams, la formation et l’assistance technique :

- [Client Web Teams](https://teams.microsoft.com)
- [Liens de téléchargement du client de bureau et mobile](https://teams.microsoft.com/downloads)
- [Vidéos de formation Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Documentation d'aide Teams](https://support.office.com/teams)

Pour obtenir des instructions sur le déploiement d’équipes et le développement d’équipes, reportez-vous [à la rubrique déploiement d’équipes](../../How-to-roll-out-teams.md) et [adoption d’équipes](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Conduire une pilote

Nous vous recommandons de commencer par déplacer deux ou trois équipes de StaffHub pour un groupe de sélection d’adoptateurs précoces. L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams. Il permet également d’identifier les champions qui peuvent favoriser l’adoption de votre organisation. S’il s’agit d’une petite entreprise qui n’a pas besoin d’une approche progressive, il est possible que vous n’ayez pas besoin de suivre les étapes décrites dans cette section pour basculer entre StaffHub et Teams.

### <a name="identify-pilot-teams"></a>Identifiez les équipes pilotes

Contactez-vous pour identifier deux ou trois équipes pilote. Tous les membres de l’équipe doivent s’engager à utiliser les Shifts dans teams pour gérer leur planning et communiquer et collaborer entre eux.

### <a name="identify-team-champions"></a>Identifier les champions d’équipe

Identifiez des champions au sein des équipes pilote et inscrivez-les pour favoriser la sensibilisation des équipes. Les champions d’équipe ont une passion quant à leur fonction, en partageant leurs propres formations afin de fournir une assistance et des recommandations aux membres de l’équipe. Les champions d’équipe peuvent être propriétaires d’équipes ou dirigeants.

Les champions doivent s’assurer que les membres de l’équipe sont configurés en consacrant du temps à tous [les](../../get-clients.md)utilisateurs, à se connecter à teams et à consulter leur planning par équipes, et à discuter avec eux. Les utilisateurs qui connaissent déjà StaffHub seront rapidement opérationnels en équipe. Vous pouvez également les [désigner pour une aide supplémentaire](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) .

### <a name="move-a-staffhub-team"></a>Déplacer une équipe StaffHub

Pour déplacer une équipe StaffHub à la fois, procédez comme suit. Nous recommandons cette approche pour vos équipes pilote. Par la suite, lorsque vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes de StaffHub](#move-your-staffhub-teams) pour savoir comment déplacer plusieurs équipes à la fois.

Exécutez la commande suivante pour déplacer une équipe StaffHub.

```
Move-StaffHubTeam -TeamId <String>
```
Example

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Voici un exemple de réponse que vous obtenez lorsque vous envoyez une demande de migration d’une équipe StaffHub vers Teams.

```
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Pour vérifier l’état d’une demande de déplacement, exécutez la commande suivante.

```
Get-TeamMigrationJobStatus <String>
```
Example

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.

```
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Déplacer des fichiers d’une équipe StaffHub vers teams

Cette étape ne s’applique qu’aux équipes de StaffHub que vous avez déplacées vers Teams. Vous pouvez déplacer des fichiers directement dans SharePoint Online ou à l’aide de PowerShell.

#### <a name="in-sharepoint-online"></a>Dans SharePoint Online

Découvrez [Comment déplacer des fichiers dans SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Utiliser PowerShell

Téléchargez et installez [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), si ce n’est déjà fait. Il contient les applets de service nécessaires pour déplacer des fichiers.  

Utilisez l’applet de [connexion Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) pour vous connecter au site d’équipe SharePoint Online.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Pour chaque fichier que vous souhaitez déplacer de StaffHub vers Teams, utilisez l’applet de passe [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) pour déplacer le fichier.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Pour déplacer plusieurs fichiers, effectuez une boucle sur les fichiers et exécutez la deuxième commande sur la boucle. Vous n’avez pas besoin de répéter la première commande si la session reste active.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Aller au-delà de votre pilote et déplacer toutes les équipes de StaffHub

### <a name="raise-awareness"></a>Sensibiliser

Lorsque vous êtes prêt à aller au-delà de vos équipes pilote et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important d’abord communiquer le changement au sein de votre organisation. Vous pouvez diffuser le mot sur les Shifts et la transition vers teams pour susciter une sensibilisation, susciter une excitation et conduire une adoption.

### <a name="move-your-staffhub-teams"></a>Déplacer vos équipes StaffHub

Suivez ces étapes pour déplacer en bloc StaffHub Teams. Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques. Si vous voulez déplacer les équipes StaffHub une par une, voir [déplacer une équipe StaffHub](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Déplacer toutes les équipes de StaffHub

Exécutez la commande suivante pour obtenir la liste de toutes les équipes de StaffHub au sein de votre organisation.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Voici un exemple de réponse.

Dans le cas d’une équipe qui a déjà été déplacée vers teams ou qui existe déjà dans Teams, le jobId sera « nul », car il n’est pas nécessaire de soumettre une demande de transfert à cette équipe.

```
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Déplacer des équipes StaffHub spécifiques

Exécutez la commande suivante pour obtenir la liste de tous les ID d’équipe StaffHub au sein de votre organisation.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Dans les résultats renvoyés par `Get-StaffHubteamsForTenant` l’applet de requête que vous avez exécutée précédemment, sélectionnez les ID d’équipe que vous voulez déplacer, puis ajoutez-les à un fichier de valeurs séparées par des virgules (CSV).

Voici un exemple de mise en forme du fichier CSV.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Après avoir créé le fichier CSV, exécutez ce qui suit pour déplacer les équipes que vous avez spécifiées dans le fichier CSV.

```
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Vérifier que vos équipes StaffHub ont été déplacées vers teams

Exécutez la commande suivante pour obtenir la liste de toutes les équipes dans les équipes de votre organisation. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Déplacer des fichiers de vos équipes StaffHub vers teams

Si les équipes de StaffHub que vous avez déplacées contiennent des fichiers que vous voulez déplacer vers Teams, voir [déplacer des fichiers d’une équipe StaffHub vers](#move-files-from-a-staffhub-team-to-teams)Microsoft Teams.

## <a name="monitor-teams-usage"></a>Surveiller l’utilisation des équipes

Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous fournir des informations sur la priorité des efforts de formation et de communication au sein de votre organisation. Vous pouvez exécuter des rapports qui décrivent l’utilisation globale des équipes, les types d’activités exécutées par les utilisateurs dans Teams, le mode de connexion des utilisateurs aux équipes, etc. Pour plus d’informations, reportez-vous à la rubrique Création de rapports d’activité dans [le centre d’administration Microsoft teams](../../teams-analytics-and-reports/teams-reporting-reference.md) et [dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Résolution des problèmes

**Obtenir plus d’informations sur les erreurs d’échec**

Exécutez la commande suivante pour obtenir plus d’informations sur les erreurs de « défaillance » qui se produisent lorsque vous tentez de déplacer une équipe :

```
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

Vous verrez l’un des statuts suivants renvoyés : réussite, échec, inprogression, en file d’attente.

Si « Failure » est retourné, exécutez la commande suivante pour obtenir plus d’informations sur l’erreur :

```
$res.Result.Error.Innererror
```

**Lorsque vous tentez de déplacer une équipe StaffHub, l’état indique « échec » et vous recevez un message d’erreur « Impossible de récupérer les catégories SKU applicables pour l’utilisateur ».**

Cela peut se produire si le ou les membres d’une équipe n’ont pas de licence Teams. Accédez à portal.office.com, repérez le groupe, puis vérifiez que les membres du groupe reçoivent une licence d’équipe.

**Lorsque vous tentez de déplacer une équipe StaffHub, l’état indique « échec » et le message d’erreur « propriétaire de l’équipe introuvable » s’affiche**

Cela peut se produire si le groupe associé à l’équipe StaffHub ne possède pas de propriétaire d’équipe. Accédez à portal.office.com, recherchez le groupe, puis ajoutez un ou plusieurs propriétaires au groupe.

**Lorsque vous tentez de déplacer les fichiers de StaffHub vers Teams, vous recevez un message d’erreur « autorisation refusée ».**

Cela risque de se produire si vous essayez de déplacer des fichiers dans un groupe Office 365 privé dont vous n’êtes pas membre. Si tel est le cas, utilisez l’applet de demande [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) pour vous ajouter à l’équipe StaffHub, puis déplacer les fichiers. Après avoir déplacé les fichiers, utilisez l’applet de passe [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) pour vous supprimer de l’équipe. 

**Lorsque vous tentez de déplacer les fichiers de StaffHub vers Teams, un message d’erreur indiquant que le dossier général n’existe pas s’affiche.**

Exécutez la commande suivante pour ajouter le dossier général à SharePoint, puis réessayez :

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Sujets associés
- [Comment mettre en place Microsoft Teams](../../How-to-roll-out-teams.md)
- [Fin de parcours pour Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Gérer l’application Shifts pour votre organisation dans Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Référence PowerShell StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
