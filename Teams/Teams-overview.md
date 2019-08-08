---
title: Bienvenue dans Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.date: 06/18/2019
audience: admin
ms.reviewer: LolaJ
description: Rechercher le parcours approprié pour le déploiement de Microsoft Teams dans votre organisation. Découvrez l’infrastructure de Teams et son utilisation avec Office 365.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9db6048a9d92144506e9ddf9b75e32b47da62ec
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239208"
---
# <a name="welcome-to-microsoft-teams"></a>Bienvenue dans Microsoft Teams
Si vous êtes l’administrateur de Microsoft Teams dans votre organisation, vous êtes au bon endroit. Lorsque vous êtes prêt à commencer avec Teams, commencez avec [Comment mettre en place Teams](How-to-roll-out-teams.md).

Si vous recherchez de l’aide pour les utilisateurs finaux Teams, cliquez sur **Aide** sur le côté gauche de l’application ou accédez au [centre d’aide de Microsoft Teams](https://support.office.com/teams). Pour une formation, accédez à [Formation Microsoft Teams](training-microsoft-teams-landing-page.md). 



Si vous débutez avec Teams et que vous voulez en savoir plus, regardez notre courte vidéo de bienvenue dans Teams (55 secondes).

> [!VIDEO https://www.youtube.com/embed/s3aQV3T0D6c]


## <a name="teams-architecture"></a>Architecture Teams

Teams est basé sur les groupes Office 365, Microsoft Graph et le même niveau de sécurité, de conformité et de facilité de gestion que le reste d’Office 365. Teams utilise les identités stockées dans Azure Active Directory (Azure AD). 

Pour voir où Teams se situe dans le contexte de Microsoft 365, consultez ce poster de l’architecture : [Teams dans le cadre de Microsoft 365](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

Lorsque vous créez une équipe, voici ce que est créé :
- Un nouveau [groupe Office 365](office-365-groups.md)
- Un site [SharePoint Online](sharepoint-onedrive-interact.md) et une bibliothèque de documents pour stocker les fichiers de l’équipe
- Une boîte aux lettres et un calendrier partagés [Exchange Online](exchange-teams-interact.md)
- Un bloc-notes OneNote
- Des liens dans des applications Office 365 telles que le Planificateur et Power BI

Lorsque vous créez une équipe à partir d'un groupe existant, les membres, le site, la boîte aux lettres et le bloc-notes de cette équipe sont transférés dans Teams. Pour en savoir plus, consultez ce poster : [Groupes dans Microsoft 365 pour les Architectes d’informatique](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

Pour personnaliser et étendre Teams, ajoutez des applications tierces via [des applications, des robots et des connecteurs](deploy-apps-microsoft-teams-landing-page.md). Avec Teams, vous pouvez inclure des personnes de l’extérieur de votre organisation en [les ajoutant en tant qu’invitées](guest-access.md) à une équipe ou un canal. Comme partie intégrante d’Office 365, Teams fournit une [plateforme de développement](https://docs.microsoft.com/microsoftteams/platform) robuste qui vous permet de créer le nœud central pour le travail d’équipe dont vous avez besoin pour votre organisation. 

> [!TIP]
> Pour approfondir l’architecture de Teams, regardez les vidéos sur l’[Academy plateforme Teams](https://aka.ms/TeamsPlatformAcademy).


## <a name="managing-teams"></a>Gestion de Teams

En tant qu’administrateur, vous allez gérer Teams via le centre d’administration de Microsoft Teams. Pour en savoir plus :
- [Utiliser des rôles d’administrateur pour gérer Teams](using-admin-roles.md)
- [Gérer Teams dans le centre d’administration Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)
- [Gérer Teams lors de la transition vers le nouveau Centre d’administration de Microsoft Teams](manage-teams-in-modern-portal.md)
- [Activer les fonctionnalités de Teams dans votre organisation Office 365](enable-features-office-365.md)

Pour rester au fait des nouveautés dans Teams et tous les autres produits Office 365 et services dans votre organisation, veillez à consulter le [Centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) et la [Feuille de route Teams](https://www.microsoft.com/microsoft-365/roadmap?rtc=1%26filters=Microsoft%20Teams%26searchterms=microsoft%2Cteams). Vous serez informé des fonctionnalités nouvelles et mises à jour, des modifications prévues et des problèmes. 

## <a name="upgrade-from-skype-for-business-to-teams"></a>Mise à niveau de Skype Entreprise vers Teams
Teams est le client principal pour des communications intelligentes dans Office 365, remplaçant Skype Entreprise Online au fil du temps. Pour en savoir plus sur les nouvelles fonctionnalités disponibles dans Teams, consultez la [Feuille de route de Microsoft 365](https://aka.ms/O365Roadmap). Pour compléter les fonctionnalités de conversation permanente et de messagerie, Teams offre une expérience de réunion et d’appels complète, avec des fonctions vocales et vidéo prédéfinies et entièrement intégrées. Consultez la rubrique [Teams est maintenant une solution de réunion et d’appel complète](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-is-now-a-complete-meeting-and-calling-solution/ba-p/236042) dans le blog Microsoft Teams.

Si vous exécutez Skype Entreprise et que vous êtes prêt à effectuer la mise à niveau vers Teams, ou si vous exécutez Skype Entreprise et Teams côte à côte et que vous êtes prêt à passer entièrement à Teams, nous avons les outils, les conseils et les guides pour vous aider à réussir votre transition. Pour plus d’informations, voir [Mise à niveau vers Teams](upgrade-start-here.md).

## <a name="teamwork-and-office-365"></a>Travail d’équipe et Office 365
Chaque équipe est différente, il n’existe pas une seule et même approche de la collaboration. Office 365 est destiné à répondre aux besoins uniques de chaque équipe, en permettant de communiquer, collaborer et faire plus avec des applications intégrées dédiées. 

Lorsque vous choisissez les applications et services Office 365 que vous allez utiliser, pensez au travail que fait votre organisation et aux types de conversations que doivent avoir vos équipes. 

- **Teams**, un nœud central pour le travail d’équipe où des personnes qui travaillent en étroite collaboration sur des projets centraux, y compris de l’extérieur de votre organisation, peuvent communiquer et collaborer activement en temps réel. Ayez une conversation directement où le travail se fait, qu’il s’agisse de rédiger en commun un document, d’avoir une réunion ou de travailler ensemble dans d’autres applications et services. Teams est l’endroit où avoir des conversations informelles, retravailler rapidement sur un projet, travailler avec les fichiers d'une équipe et collaborer sur des produits partagés. 

- **Outlook** pour collaborer dans l’environnement de messagerie familier et d’une manière plus formelle et structurée ou lorsqu’une communication ciblée et directe est nécessaire. 

- **SharePoint** pour les sites, portails, services de contenu intelligents, l'automatisation de processus métiers et la recherche dans l'entreprise. SharePoint place le contenu au centre du travail d’équipe, rendant tous les types de contenu facilement partageables et accessibles entre les équipes. Une intégration étroite à Outlook, Yammer et Teams permet une collaboration sur du contenu homogène entre les expériences de conversation.

- **OneDrive Entreprise** pour stocker des fichiers et les partager avec les personnes qu'un utilisateur invite. Le contenu qu'un utilisateur enregistre dans OneDrive Entreprise est privé jusqu’à ce qu’il le partage avec d’autres personnes, ce qui en fait la meilleure option pour stocker les documents personnels et d’ébauche qui ne sont pas destinés ou prêts à être partagés.

- **Yammer** pour connecter les personnes de l’organisation. Proposez des initiatives à l’échelle de l’entreprise, partagez les meilleures pratiques et créez des communautés autour de sujets d’intérêt, domaines ou pratiques communs. Échangez des idées pour favoriser des discussions ouvertes avec les personnes de l’entreprise.

- Les **applications Office** sont tous les outils familiers que les personnes connaissent et utilisent régulièrement, incluant Word, Excel, PowerPoint et OneNote. 

## <a name="teams-content-updates"></a>Mises à jour de contenu Teams

Consultez la [liste hebdomadaire des sujets Teams qui ont été mis à jour](teams-updates.md).

## <a name="teams-known-issues"></a>Problèmes connus dans Teams

Voir[Problèmes connus dans Teams](Known-issues.md).

## <a name="teams-client-release-notes"></a>Notes de publication du client Teams

Voir[Nouveautés d’Office](https://support.office.com/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de).

