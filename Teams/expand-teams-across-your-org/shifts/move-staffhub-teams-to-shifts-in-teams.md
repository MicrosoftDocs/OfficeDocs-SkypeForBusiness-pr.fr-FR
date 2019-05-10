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
description: Découvrez comment déplacer vos équipes Microsoft StaffHub et programmer des données pour les déplacements dans Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865049"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Atteindre vos équipes Microsoft StaffHub équipes dans Microsoft Teams

> [!IMPORTANT]
> Effet 2019, octobre 1, Microsoft StaffHub sera être retirée. Nous créons StaffHub fonctionnalités dans Microsoft Teams. Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps. StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019. Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes. Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).

> La fonctionnalité abordée dans cet article n’a pas encore été publiée. Il est été annoncé et sera bientôt disponible, vers le milieu de mai 2019. Si vous êtes un administrateur, vous pouvez savoir lorsqu’il sera disponible dans le centre de messages (dans le [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home)).

L’application d’équipes dans les équipes fournit une approche simple de gérer les planifications et le flux de constant de permutations MAJ et les annulations qui se produisent au quotidien. Membres de l’équipe peuvent accéder à son calendrier et informations MAJ directement dans l’application sur leurs appareils pour définir leurs préférences, gérer leurs calendriers et durée hors de la demande.

Cet article vous explique comment déplacer les équipes StaffHub de votre organisation et planifier les données aux équipes de travail en équipe. Si vous êtes une petite entreprise avec un ou deux équipes StaffHub ou une grande entreprise avec des centaines de StaffHub équipes, vous trouverez les instructions d’administration que vous avez besoin pour réussir votre transition aux équipes réussie.

Vous devez être un administrateur global pour effectuer les étapes décrites dans cet article. Si vous n’avez pas déjà fait, jetez un œil via le [retrait StaffHub FAQ](microsoft-staffhub-to-be-retired.md) pour obtenir des réponses à des questions, que vous devrez peut-être. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Ce que vous devez savoir sur le déplacement aux équipes

### <a name="when-to-move-to-teams"></a>Quand déplacer aux équipes

Effet 2019, octobre 1, StaffHub système être retirée. Nous vous invitons à commencer à utiliser les équipes aujourd'hui et commencer à effectuer la transition de votre organisation équipes et les utilisateurs de StaffHub. Avec la gestion de la planification en cours de la fonctionnalité plus fréquemment utilisées dans StaffHub, nous vous recommandons de qu'utiliser l’application d’équipes dans les équipes avançant.

### <a name="what-is-moved-to-teams"></a>Quel est déplacé vers les équipes

Détails de l’utilisateur, les informations de planification et données conversation et de fichiers sont passées aux équipes. Cela inclut l’appartenance de l’équipe, les planifications de l’équipe et les conversations et les fichiers au cours des 90 derniers jours.

Chaque équipe StaffHub a besoin d’un groupe de 365 Office correspondant. Si une équipe StaffHub ne possède pas un groupe d’Office 365 lui est associé, une est automatiquement créée pour prendre en charge la transition. Étant donné la différence de l’équipe et le groupe d’affectation de noms entre les équipes et StaffHub, vous pouvez voir un nom différent de l’équipe dans les équipes.

Transition entre les équipes de StaffHub aux équipes, les utilisateurs n’aura plus accès à leurs planifications dans StaffHub et sont redirigés vers les équipes de travail en équipe. Nous vous recommandons de que vous communiquez ce changement dans votre organisation pour réduire l’interruption et encourager les utilisateurs à adopter et Explorer les équipes. Si vous avez Azure AD Premium, vous pouvez [exécuter un rapport](run-report-to-show-staffhub-usage.md) pour obtenir une liste d’utilisateurs StaffHub dans votre organisation qui ont besoin de savoir à propos de ce changement.  

Il n’existe aucune option de restauration après avoir déplacé une équipe StaffHub aux équipes.

### <a name="user-experience-when-you-move-a-team"></a>Expérience utilisateur lorsque vous déplacez une équipe

Il est temps d’arrêt minimal (moins d’une seconde, le cas échéant) pour les utilisateurs lors de leur équipe est commutée de StaffHub aux équipes de travail en équipe. Les utilisateurs peuvent continuer à l’aide de StaffHub jusqu'à ce que le déplacement aux équipes est terminé. Le déplacement est terminé, membres de l’équipe seront affiche un message pour l’informer que dont ils ont besoin commencer à utiliser des déplacements dans les équipes pour accéder à leur planification d’équipe. Voici un exemple du message que les utilisateurs voient.

![Exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub est déplacé vers équipes.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Exemple du message que les utilisateurs voient dans StaffHub une fois que l’équipe StaffHub est déplacé vers les équipes")

## <a name="prepare"></a>Préparer

Voici comment préparer le déplacement aux équipes.

### <a name="assign-teams-licenses"></a>Assigner des licences Teams

Chaque utilisateur doit disposer d’une licence Microsoft 365 ou Office 365 active à partir [d’un plan éligible](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) et doit être attribué une licence d’équipes. Attribution des licences équipes aux utilisateurs leur donne accès aux équipes.

Gérer les licences d’équipes dans le centre d’administration Microsoft 365. Pour plus d’informations, voir [gérer l’accès utilisateur aux équipes](../../user-access.md).

> [!NOTE]
> Si votre organisation utilise Skype pour les entreprises et vous n’êtes pas prêt à passer tous vos utilisateurs à des équipes, vous pouvez activer les équipes pour vos employés Firstline qui peut ensuite exécuter les équipes à côté de Skype pour les entreprises. Dans ce mode de coexistence, appelé *(îles)*, chaque application client fonctionne comme une solution distincte. Pour plus d’informations, voir [comprendre les équipes et Skype pour l’interopérabilité et coexistence d’entreprise](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Mise en service des comptes pour les utilisateurs StaffHub qui n’ont pas d’identité dans Azure AD

Chaque responsable et un membre de l’équipe doivent avoir une identité dans Azure Active Directory (AD Azure). Si un utilisateur n’a pas encore une identité dans Azure AD, configurez un compte pour eux. Voici comment procéder.

- Les responsables et les propriétaires de l’équipe StaffHub peuvent convertir un compte factice ou inactif et le lier à un compte dans StaffHub mis en service en modifiant l’adresse de messagerie de l’utilisateur à un nom UPN valid dans la page Paramètres de l’équipe StaffHub.

- Administrateurs peuvent exécuter l' [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) et sauvegarder des applets de commande [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) pour supprimer un compte non mis en service d’une équipe StaffHub et ajoutez le compte à l’aide de l’UPN.

### <a name="install-the-staffhub-powershell-module"></a>Installer le module PowerShell Microsoft StaffHub

Si vous n’avez pas déjà fait, [installez le module StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Lorsque vous déplacez une équipe StaffHub, la demande de déplacement vérifie les conditions préalables. Voici les raisons de l’échec une demande de déplacement :

- L’utilisateur connecté n’est pas un administrateur global
- Les équipes est désactivé pour tous les utilisateurs dans le client
- Création de groupes d’Office 365 est désactivée dans le client
- L’ID d’équipe StaffHub n’est pas valide ou n’a aucun membre
- L’équipe StaffHub inclut des membres qui ne sont pas liés à un compte Azure AD  

## <a name="run-a-pilot"></a>Exécuter un projet pilote

Nous vous recommandons de que commencer par le déplacement de deux ou trois équipes StaffHub pour un groupe particulier de premiers. Exécuter un pilote vous permet d’affiner votre plan de transition et vérifiez que vous êtes prêt à passer des équipes de StaffHub ensemble de l’entreprise à des équipes. Il identifie également les champions qui peuvent aider à encourager l’adoption au sein de votre organisation. Si vous êtes une petite entreprise qui n’ont pas besoin une approche progressive, les étapes décrites dans cette section peuvent être il que vous suffit de passer StaffHub aux équipes.

### <a name="identify-pilot-teams"></a>Identifier les équipes pilotes

Atteindre pour identifier les deux ou trois équipes pilotes. Tous les membres de l’équipe doivent valider à l’utilisation d’équipes dans les équipes à gérer leurs calendriers et communiquer et collaborer avec eux.

### <a name="identify-team-champions"></a>Identifier les champions de l’équipe

Identifier les champions équipes de pilote et les inscrire pour vous aider à faire connaître les déplacements. Champions de l’équipe sont passionnées sur dans ce cas, le partage de leurs propres connaissances pour offrir une prise en charge et des conseils aux membres d’équipe. Les champions de l’équipe peuvent être propriétaires d’équipe ou les responsables.

Champions de l’équipe devraient vous assurer que les membres de l’équipe sont définis par heure dédiant pour tout le monde pour [obtenir les clients d’équipes](../../get-clients.md), se connecter à des équipes et extrayez planifications leurs équipes et démarrer la conversation entre eux. Les utilisateurs qui sont déjà familiarisés avec StaffHub seront en cours d’exécution rapidement en équipe. Vous pouvez également qu’ils pointent vers [Des équipes aide](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) pour une assistance supplémentaire.

### <a name="move-a-staffhub-team-coming-soon"></a>Déplacer une équipe StaffHub (bientôt disponible)

Utilisez ces étapes pour déplacer une équipe StaffHub à la fois. Nous vous recommandons cette approche pour les équipes de votre pilotes. Plus tard, lorsque vous êtes prêt à passer des équipes de StaffHub ensemble de l’entreprise, voir [déplacer vos équipes StaffHub](#move-your-staffhub-teams-coming-soon) pour connaître les étapes sur la façon de déplacer plusieurs équipes à la fois.

Exécutez la commande suivante pour déplacer une équipe StaffHub.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Voici un exemple de la réponse que vous obtenez lorsque vous envoyez une demande de déplacement d’une équipe StaffHub aux équipes.

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

Voici un exemple de la réponse que vous obtenez lorsqu’un déplacement est en cours.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Effectuer la transition à partir de StaffHub aux équipes

### <a name="raise-awareness"></a>Sensibilisation

Lorsque vous êtes prêt à aller au-delà de vos équipes pilotes et déplacer les équipes de votre organisation StaffHub aux équipes, il est important de communiquer tout d’abord la modification au sein de votre organisation. Diffusion équipes et la transition vers les équipes pour sensibiliser, générer enthousiasme et d’adoption du lecteur.

### <a name="move-your-staffhub-teams-coming-soon"></a>Déplacer vos équipes StaffHub (bientôt disponible)

Utilisez ces étapes pour déplacer des équipes StaffHub en bloc. Vous pouvez choisir déplacer les équipes StaffHub ensemble de l’entreprise ou des équipes StaffHub spécifiques. Si vous souhaitez déplacer que les équipes StaffHub un à la fois, voir [déplacer une équipe StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Déplacer toutes les équipes StaffHub (bientôt disponible)

Exécutez ce qui suit pour obtenir une liste de toutes les équipes StaffHub dans votre organisation.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Ensuite, exécutez la commande suivante pour déplacer toutes les équipes.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Voici un exemple de la réponse.

Pour une équipe qui a été déjà déplacée aux équipes ou existe déjà dans les équipes, le jobId sera « null » comme une tâche n’a pas besoin d’être envoyés à déplacer que l’équipe.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Déplacer des équipes StaffHub spécifiques (bientôt disponible)

Exécutez ce qui suit pour obtenir une liste de tous les StaffHub équipe ID dans votre organisation.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Dans les résultats renvoyés par la `Get-StaffHubteamsForTenant` applet de commande que vous avez exécuté précédemment, sélectionnez les ID de l’équipe vous souhaitez déplacer, puis les ajouter à un fichier de valeurs séparées par des virgules (CSV).

Voici un exemple de la façon dont le fichier CSV doit être mis en forme.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000|

Après avoir créé le fichier CSV, exécutez la commande suivante pour déplacer les équipes que vous avez spécifié dans le fichier CSV.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Vérifiez que vos équipes StaffHub ont déplacés aux équipes (bientôt disponible)

Exécutez ce qui suit pour obtenir la liste de toutes les équipes de déplacements au sein de votre organisation. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Surveiller l’utilisation d’équipes

Rapports d’utilisation peuvent vous aider à mieux comprendre les modèles d’utilisation et vous donner des idées permettant de hiérarchiser les efforts de formation et de communication au sein de votre organisation. Équipes étant une application dans les équipes, vous pouvez afficher l’utilisation par le biais de rapports d’équipes. Pour plus d’informations, voir [équipes de création de rapports dans le centre d’administration Microsoft équipes](../../teams-analytics-and-reports/teams-reporting-reference.md) et des [rapports d’activité équipes dans le centre d’administration Microsoft 365](../../teams-activity-reports.md).

## <a name="related-topics"></a>Voir aussi
- [Fin de parcours pour Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)
- [Gérer l’application Shifts pour votre organisation dans Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Référence StaffHub PowerShell](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
