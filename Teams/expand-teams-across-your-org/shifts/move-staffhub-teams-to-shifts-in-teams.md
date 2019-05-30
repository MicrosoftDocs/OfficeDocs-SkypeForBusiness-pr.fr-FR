---
title: Déplacer vos équipes de Microsoft StaffHub vers Shifts dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et planifier des données en équipes dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548293"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Déplacer vos équipes Microsoft StaffHub vers des équipes dans Microsoft teams

> [!IMPORTANT]
> À compter du 1er octobre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub ne fonctionnera pas pour tous les utilisateurs du 1er octobre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).

> La fonctionnalité décrite dans cet article n’a pas encore été publiée. Il a été annoncé et sera bientôt disponible à partir du 2019 du 1er juin. Si vous êtes un administrateur, vous pouvez en savoir plus sur le moment où il sera disponible dans le centre de messages (dans le [Centre d’administration 365 Microsoft](https://portal.office.com/adminportal/home)).

L’application Shifts dans teams fournit une méthode simple pour gérer les plannings et le flux constant de permutations et d’annulations de Shift qui se produisent quotidiennement. Les membres d’une équipe peuvent accéder à leur planning et leur transférer directement dans l’application et sur leurs appareils pour définir leurs préférences, gérer leur planning et demander un congé.

Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier vos données en vue de leur déplacement dans Teams. Que vous soyez une petite entreprise disposant d’une ou de deux équipes StaffHub ou d’une grande entreprise ayant des centaines d’équipes, vous trouverez ci-dessous les conseils d’administration dont vous avez besoin pour faciliter la transition vers les équipes.

Pour pouvoir effectuer les étapes décrites dans cet article, vous devez être un administrateur général. Si vous ne l’avez pas déjà fait, consultez le [Forum aux questions de retraite StaffHub](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses aux questions que vous pourriez rencontrer. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Ce que vous devez savoir sur le déplacement dans teams

### <a name="when-to-move-to-teams"></a>Quand déplacer vers teams

À compter du 1er octobre 2019, StaffHub sera supprimé. Nous vous encourageons à commencer à utiliser teams dès aujourd’hui et à migrer les équipes et les utilisateurs de votre organisation à partir de StaffHub. Avec la gestion des plannings étant la fonctionnalité la plus couramment utilisée dans StaffHub, nous vous recommandons d’utiliser l’application Shifts dans les équipes qui progressent.

### <a name="what-is-moved-to-teams"></a>Ce qui est déplacé vers teams

Les détails de l’utilisateur, les informations de calendrier et les discussions et les données de fichier sont migrés vers Teams. Il s’agit de l’appartenance à une équipe, des plannings d’équipe, des conversations et des fichiers aux derniers 90 jours.

Chaque équipe StaffHub doit avoir un groupe Office 365 correspondant. Si une équipe StaffHub n’a pas de groupe Office 365 associé, vous pouvez l’utiliser pour la prise en charge de la transition. En raison de la différence entre les noms d’équipe et de groupe entre teams et StaffHub, il est possible que vous voyiez un nom d’équipe différent dans Teams.

Lorsque vous transformez des équipes de StaffHub en équipes, les utilisateurs n’ont plus accès à leur planning dans StaffHub et sont redirigés vers des équipes dans Teams. Nous vous recommandons de communiquer ce changement au sein de votre organisation afin de limiter les perturbations et d’encourager les utilisateurs à adopter et à explorer les équipes. Si vous disposez d’Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir la liste des utilisateurs de StaffHub de votre organisation qui doivent savoir ce changement.  

Il n’existe aucune option de restauration après le déplacement d’une équipe StaffHub vers Teams.

### <a name="user-experience-when-you-move-a-team"></a>Utilisation de l’interface utilisateur lorsque vous déplacez une équipe

Il y a un minimum d’interruption de service (moins d’une seconde, le cas échéant) pour les utilisateurs lorsque leur équipe passe de StaffHub à équipes. Les utilisateurs peuvent continuer à utiliser StaffHub jusqu’à ce que le passage aux équipes soit terminé. Lorsque le déplacement est terminé, les membres de l’équipe voient s’afficher un message lui informant qu’ils doivent commencer par utiliser les Shifts dans teams pour accéder à leur planning d’équipe. Voici un exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub a été déplacée vers Teams.

![Exemple du message que les utilisateurs voient.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemple du message que les utilisateurs voient dans StaffHub après le déplacement de l’équipe StaffHub vers") teams

## <a name="prepare"></a>Prévenir

Voici comment préparer le déplacement vers Teams.

### <a name="assign-teams-licenses"></a>Assigner des licences Teams

Chaque utilisateur doit avoir une licence Microsoft 365 ou Office 365 active d' [un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et être disposant d’une licence d’équipe. L’attribution d’une licence d’équipe aux utilisateurs leur permet d’accéder à Teams.

Pour gérer les licences d’équipe, vous devez utiliser le centre d’administration 365 Microsoft. Pour en savoir plus, voir [gérer l’accès des utilisateurs aux équipes](../../user-access.md).

> [!NOTE]
> Si votre organisation utilise Skype entreprise et que vous n’êtes pas prêt à déplacer tous vos utilisateurs vers Teams, vous pouvez activer les équipes pour vos travailleurs terrain qui peuvent alors exécuter des équipes en même temps que Skype entreprise. Dans ce mode de coexistence, ** intitulé îlots, chaque application cliente fonctionne en tant que solution distincte. Pour en savoir plus, reportez-vous à la rubrique [Présentation des équipes et coexistence et interopérabilité de Skype entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Mise en service des comptes pour les utilisateurs de StaffHub qui n’ont pas d’identité dans Azure AD

Chaque responsable et membre d’équipe doit avoir une identité dans Azure Active Directory (Azure AD). Si un utilisateur n’a pas encore d’identité dans Azure AD, approvisionnez-en un. Voici comment procéder.

- Les propriétaires d’équipes et responsables de StaffHub peuvent convertir un compte fictif ou inactif et le lier à un compte approvisionné dans StaffHub en définissant l’adresse de courrier de l’utilisateur sur un UPN valide dans la page Paramètres de l’équipe StaffHub.

- Les administrateurs peuvent exécuter les applets de [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) et [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer un compte non approvisionné d’une équipe StaffHub et ajouter de nouveau le compte à l’aide du nom UPN.

### <a name="install-the-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

Si ce n’est déjà fait, [Installez le module StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Lorsque vous déplacez une équipe StaffHub, la demande de déplacement vérifie la configuration requise. Voici quelques raisons pour lesquelles il est possible qu’une demande de déplacement réussisse:

- L’utilisateur connecté n’est pas un administrateur global
- Teams est désactivé pour tous les utilisateurs du client.
- La création de groupes Office 365 est désactivée dans le client
- Le teamId StaffHub n’est pas valide ou ne possède pas de membres
- L’équipe StaffHub inclut les membres qui ne sont pas liés à un compte Azure AD  

## <a name="run-a-pilot"></a>Exécution d’un pilote

Nous vous recommandons de commencer par déplacer deux ou trois équipes de StaffHub pour un groupe de sélection d’adoptateurs précoces. L’exécution d’un pilote vous permet d’affiner votre plan de transition et de vous assurer que vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation vers Teams. Il permet également d’identifier les champions qui peuvent favoriser l’adoption de votre organisation. S’il s’agit d’une petite entreprise qui n’a pas besoin d’une approche progressive, il est possible que vous n’ayez pas besoin de suivre les étapes décrites dans cette section pour basculer entre StaffHub et Teams.

### <a name="identify-pilot-teams"></a>Identifiez les équipes pilotes

Contactez-vous pour identifier deux ou trois équipes pilote. Tous les membres de l’équipe doivent s’engager à utiliser les Shifts dans teams pour gérer leur planning et communiquer et collaborer entre eux.

### <a name="identify-team-champions"></a>Identifier les champions d’équipe

Identifiez des champions au sein des équipes pilote et inscrivez-les pour favoriser la sensibilisation des équipes. Les champions d’équipe ont une passion quant à leur fonction, en partageant leurs propres formations afin de fournir une assistance et des recommandations aux membres de l’équipe. Les champions d’équipe peuvent être propriétaires d’équipes ou dirigeants.

Les champions doivent s’assurer que les membres de l’équipe sont configurés en consacrant du temps à tous [les](../../get-clients.md)utilisateurs, à se connecter à teams et à consulter leur planning par équipes, et à discuter avec eux. Les utilisateurs qui connaissent déjà StaffHub seront rapidement opérationnels en équipe. Vous pouvez également les désigner pour [](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) une aide supplémentaire.

### <a name="move-a-staffhub-team-coming-soon"></a>Déplacer une équipe StaffHub (bientôt disponible)

Pour déplacer une équipe StaffHub à la fois, procédez comme suit. Nous recommandons cette approche pour vos équipes pilote. Par la suite, lorsque vous êtes prêt à déplacer toutes les équipes StaffHub de votre organisation, voir [déplacer vos équipes de StaffHub](#move-your-staffhub-teams-coming-soon) pour savoir comment déplacer plusieurs équipes à la fois.

Exécutez la commande suivante pour déplacer une équipe StaffHub.

```
Move-StaffHubTeam -TeamId <String>

Sample:

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

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

Voici un exemple de réponse que vous obtenez lorsqu’un déplacement est en cours.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Effectuer la transition de StaffHub à teams

### <a name="raise-awareness"></a>Sensibiliser

Lorsque vous êtes prêt à aller au-delà de vos équipes pilote et à déplacer les équipes StaffHub de votre organisation vers Teams, il est important d’abord communiquer le changement au sein de votre organisation. Vous pouvez diffuser le mot sur les Shifts et la transition vers teams pour susciter une sensibilisation, susciter une excitation et conduire une adoption.

### <a name="move-your-staffhub-teams-coming-soon"></a>Déplacez vos équipes StaffHub (bientôt disponible)

Suivez ces étapes pour déplacer en bloc StaffHub Teams. Vous pouvez choisir de déplacer toutes les équipes StaffHub de votre organisation ou de déplacer des équipes StaffHub spécifiques. Si vous voulez déplacer les équipes StaffHub une par une, voir [déplacer une équipe StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Déplacer toutes les équipes de StaffHub (bientôt disponible)

Exécutez la commande suivante pour obtenir la liste de toutes les équipes de StaffHub au sein de votre organisation.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Voici un exemple de réponse.

Dans le cas d’une équipe qui a déjà été déplacée vers teams ou qui existe déjà dans Teams, le jobId sera «nul», car il n’est pas nécessaire de soumettre une demande de transfert à cette équipe.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Déplacer des équipes StaffHub spécifiques (bientôt disponible)

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
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Confirmez que vos équipes StaffHub ont été déplacées vers Teams (bientôt disponible)

Exécutez la commande suivante pour obtenir la liste de toutes les équipes dans les équipes de votre organisation. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Surveiller l’utilisation des équipes

Les rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous fournir des informations sur la priorité des efforts de formation et de communication au sein de votre organisation. Comme Shifts est une application dans Teams, vous pouvez voir l’utilisation via des rapports d’équipes. Pour plus d’informations, reportez-vous à la rubrique Création de rapports d’activité dans [le centre d’administration Microsoft teams](../../teams-analytics-and-reports/teams-reporting-reference.md) et [dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Voir aussi
- [Fin de parcours pour Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Gérer l’application Shifts pour votre organisation dans Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Référence PowerShell StaffHub](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
