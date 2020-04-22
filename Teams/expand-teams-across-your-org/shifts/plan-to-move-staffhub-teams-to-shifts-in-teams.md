---
title: Planifier le déplacement de vos équipes StaffHub vers les équipes
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenez des conseils pour migrer vos équipes StaffHub vers des équipes dans Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f296beffa5d9d97bd34035a80cac8068783cea54
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780613"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Planifier le déplacement de vos équipes StaffHub vers les équipes de Microsoft teams

> [!IMPORTANT]
> À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md). 

Le passage de StaffHub à teams démarre lorsque vous commencez à planifier le changement. Pour garantir la réussite de votre déplacement vers Teams, nous avons créé un exemple de chronologie illustrant un plan de transition standard. L’exemple de chronologie décrit les activités de planification pour le déplacement et vous guide dans le passage des équipes StaffHub de votre organisation aux équipes.

Servez-vous de la chronologie en guise d’instructions pour planifier votre passage de StaffHub à Teams, puis personnalisez-le en fonction des besoins de votre organisation. Veillez à examiner les ressources liées aux étapes de la chronologie.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Préparer le déplacement de vos équipes StaffHub vers teams

|Étape |Aide  |Ressources |
|---------|---------|---------|
|1    |Préparer et identifier les parties prenantes         |         |
|deuxième     |Passez en revue la documentation sur le passage de StaffHub aux équipes et aux équipes dans l’intégration         |[StaffHub à déretraiter](microsoft-staffhub-to-be-retired.md)<br><br>[Déplacez vos équipes StaffHub vers des équipes dans teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Prise en main de Teams](../../get-started-with-teams-quick-start.md)         |
|3    |Activer les groupes Microsoft 365 pour votre organisation        |[Groupes et équipes Microsoft 365](../../Office-365-groups.md)      |
|4    |Vérifiez que les conditions préalables sont remplies         |[Vérifier que les conditions préalables sont remplies](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Attribution de licences teams aux utilisateurs de StaffHub au sein de votre organisation|[Assigner des licences Teams](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Gérer l’accès des utilisateurs à Microsoft Teams](../../user-access.md)      |
|6    |Installer le module PowerShell Microsoft StaffHub        |[Installer le module PowerShell Microsoft StaffHub](install-the-staffhub-powershell-module.md)        |
|7     |Déterminez la chronologie et identifiez les utilisateurs de StaffHub pour le déménagement aux équipes       |[Exécuter un rapport pour afficher l’utilisation effective de StaffHub](run-report-to-show-staffhub-usage.md) |
|version8     |Identifier les utilisateurs d’StaffHub qui n’ont pas de compte Azure AD (qui s’affiche comme « inactif » dans StaffHub) et de lier un compte pour eux     |[Créer un lien vers un compte Azure AD pour les membres de l’équipe StaffHub qui n’en ont pas](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|09    |Créer du contenu de formation pour les utilisateurs adaptés à votre organisation         |[Préparer un plan de vérification de l’utilisateur pour teams](../../upgrade-user-readiness.md)     |
|0,10    |Communiquer aux utilisateurs de StaffHub à propos de la transition aux équipes dans teams         |[StaffHub-XXXXXXX XXXXXXX XXXXXXX XXXXXXX XXXXXXX](staffhub-to-teams-email-template.md)         |
|27,9     |Installer les clients teams         |[Obtenir des clients pour Teams](../../get-clients.md) |
|midi    |Affectez la stratégie de configuration de l’application FirstLineWorker aux utilisateurs (ou créez et attribuez une stratégie de configuration d’application personnalisée) pour épingler l’application Shifts aux clients Teams.  |[Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|n°13     |Former les utilisateurs sur l’utilisation des équipes et des équipes         |[Utilisateurs intégrés à teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Documentation d’aide sur les Shifts](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Documentation d'aide Teams](https://support.office.com/teams)<br><br>[Vidéos de formation Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Passez en revue la liste de vos équipes StaffHub pour vous assurer que tous les utilisateurs de ces équipes doivent être déplacés vers Teams. Supprimez les utilisateurs qui ne doivent pas figurer dans l’échéancier. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Déplacer les équipes StaffHub de votre organisation vers teams

|Étape |Aide |Ressources  |
|---------|---------|---------|
|1  |Identifier une équipe pilote et déplacer une équipe          |[Déplacer une équipe StaffHub](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|deuxième    |Valider l’équipe pilote et identifier les problèmes de déplacement. Mettez à jour la documentation de formation selon vos besoins.         |         |
|3     |Identifiez les équipes pilotes supplémentaires et déplacez-les cinq vers 10 équipes         |[Déplacer vos équipes StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Identifier les équipes StaffHub restantes et les déplacer dans une approche progressive         |[Déplacer vos équipes StaffHub](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Continuer à fournir une assistance technique pour les équipes et équipes         |         |
|6     |Si la réinitialisation du mot de passe libre-service est activée, exécuter un rapport pour la prise en charge des problèmes de connexion dans teams       |[Exécuter un rapport pour la configuration de la réinitialisation du mot de passe libre-service](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
