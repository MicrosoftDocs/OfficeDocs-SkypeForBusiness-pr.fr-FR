---
title: Présentation de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Découvrez Microsoft teams, son infrastructure et son utilisation avec Office 365.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b556a7293ecd6c6158a3fb1f7e882fa87defbc45
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="overview-of-microsoft-teams"></a>Présentation de Microsoft Teams
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


Microsoft Teams rassemble toutes les fonctionnalités d'Office 365, pour fournir une véritable plateforme dédiée à la communication et favoriser le travail en équipe et donner aux clients la possibilité de créer un environnement plus ouvert, fluide et numérique. Microsoft Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365. 

Prêt à l'emploi, Microsoft Teams utilise les identités stockées dans Azure Active Directory (Azure AD) et s'intègre aux autres services dans Office 365, pour créer un site SharePoint Online et une boîte aux lettre de groupe Exchange Online pour chaque équipe créée.

Toute personne disposant d’un compte de messagerie professionnels et particuliers, tels que Outlook, Gmail ou autres, peut participer en tant qu’invité dans des équipes. Tous les invités dans les équipes sont couverts par la même conformité et audit de protection que le reste de Office 365 et invités peuvent être gérées en toute sécurité dans l’annonce d’Azure. Administrateurs peuvent centraliser gérer la participation des invités dans leur environnement Office 365 et facilement afficher, ajouter ou révoquer l’accès d’invité au locataire hôte.

Teams fournit une fonctionnalité de conversation permanente, d’appels et réunions et permet d’accéder facilement aux autres composants d’Office 365, et offre également des possibilités d’extension.  Vous disposez ainsi d'une plateforme dédiée au travail en équipe qui est appropriée pour les grandes entreprises, les petites organisations et les entreprises de taille intermédiaire.  

Pour étendre les fonctionnalités de Teams, utilisez des connecteurs, onglets et bots disponibles en tant qu'[applications](https://go.microsoft.com/fwlink/?linkid=854629) pour introduire les interactions avec des informations externes, du contenu et des bots intelligents dans Teams.  

<a name="microsoft-teams-infrastructure"></a>Infrastructure de Microsoft Teams
------------------------------

Teams est basé sur des technologies Microsoft existantes interreliées par d'autres groupes Office 365. Avec le cloud de Microsoft, les organisations peuvent profiter de performances excellentes et d'une grande fiabilité lors de l'utilisation de Teams dans le cadre de leur scénario de collaboration.

Prête à l'emploi, une équipe créée dans Teams formera un groupe Office 365 avec un site SharePoint Online associé ainsi qu'une bibliothèque de documents, une boîte aux lettres Exchange Online qui sera utilisé par Teams pour stocker des informations, telles que des invitations à des réunions. Une équipe peut être créée à l'aide de groupes Office 365 existants, ce qui permet de transférer les adhésions de groupe, le contenu stocké dans SharePoint Online et dans Exchange Online vers Teams.

Pour compléter la fonctionnalité Teams comme outil de conversation permanente, qui permet de mener des conversations informelles en temps réel, Teams fournit également une expérience d'appels et de réunions basée sur l'infrastructure cloud de nouvelle génération, également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité.

Les groupes Office 365 utilisent les identités stockées dans Azure Active Directory (Azure AD) et en tant que tel, toutes les fonctionnalités d'authentification et d'autorisation dans Azure AD, comme la prise en charge de l’authentification multifacteur, sont déjà disponibles dans Teams.

L'expérience d'appels et de réunions Microsoft Teams est basée sur l'infrastructure cloud de nouvelle génération, également utilisée par Skype et Skype Entreprise. Ces investissements technologiques incluent les services cloud Azure pour le traitement multimédia et la signalisation, le codec vidéo H.264, le codec audio SILK et Opus, la résilience réseau, la télémétrie et le diagnostic de qualité.

> [!NOTE]
> En fonction des commentaires des clients, des groupes de 365 Office due à la création d’une équipe dans Microsoft Teams n’apparaît plus dans Outlook par défaut. Pour les clients que vous souhaitez poursuivre le comportement existant de l’affichage de ces groupes dans Outlook, une applet de commande PowerShell en ligne d’Exchange est fournie qui permettent le groupe pour l’expérience Outlook. Groupes créés via Outlook et activé plus tard pour les équipes continuera d’afficher dans Outlook et les équipes. Cette mise à jour sera progressivement rouleau arrière entre Outlook et équipes dans les mois à venir.


<a name="microsoft-teams-and-office-365"></a>Microsoft Teams et Office 365
------------------------------

Les besoins des groupes divergent en fonction de leur rôle et de leur mode de travail. Office 365 est conçu pour s'adapter au mode de travail unique de chaque groupe et inclut, entre autres, les applications dédiées et intégrées suivantes :

-   Outlook pour la messagerie d'entreprise, désormais inclus avec la fonctionnalité de groupe

-   SharePoint pour les sites et portails, des services de contenu intelligents, l'automatisation de processus métiers et la recherche dans l'entreprise

-   Yammer pour les connexions à l'échelle de l'entreprise

-   Skype Entreprise comme dorsale pour les fonctions audio et vidéo de l'entreprise

-   Et à présent, Microsoft Teams, le nouvel espace de travail dédié à la communication dans Office 365

Voici quelques scénarios d'utilisation courants pour chaque application dans Office 365. Pour obtenir des instructions détaillées, rendez-vous dans la [Bibliothèque de productivité FastTrack](https://go.microsoft.com/fwlink/?linkid=854630).

![Icône Microsoft Teams.](media/Overview_of_Microsoft_Teams_image1.png)

-   Utilisée par les utilisateurs et les équipes pour collaborer en temps réel dans le même groupe de membres

-   Aide les équipes qui souhaitent retravailler rapidement sur un projet tout en partageant des fichiers et en collaborant sur des livrables partagés

-   Permet aux utilisateurs de se connecter une large gamme d’outils dans leur espace de travail (par exemple, le planificateur, alimentation BI, GitHub, etc.).

![Icône Microsoft Outlook.](media/Overview_of_Microsoft_Teams_image2.png)

-   Pour les utilisateurs qui préfèrent collaborer dans l'environnement de messagerie familier et/ou de manière plus formelle et structurée

-   Fournit des processus métiers spécifiques qui requièrent l'utilisation de la messagerie pour transmettre des documents et des'informations à l'extérieur comme à l'intérieur de l'entreprise

-   Contacte les utilisateurs hors des organisations ou groupes de travail immédiats

![Icône Yammer.](media/Overview_of_Microsoft_Teams_image3.png)

-   Permet de connecter les utilisateurs dans l'organisation pour former des communautés spécialisées et partager des meilleures pratiques

-   Améliore les flux de travail inter-fonctionnels via une plateforme de flux ouverte et transparente

-   Favorise l'implication des dirigeants dans les conversations bidirectionnelles entre la direction et les employés

-   Encourage vos intervenants de première ligne à partager et recevoir des connaissances et compétences

![Icône Skype Entreprise.](media/Overview_of_Microsoft_Teams_image4.png)

-   Utilisée pour la communication et la collaboration internes et externes en temps réel avec les clients/partenaires

-   Fournit des fonctionnalités audio, vidéo et de partage de contenu pour les réunions de grandes ou petites équipes (y compris des conférences comprenant jusqu'à 10 000 participants)

-   Fournit la fonctionnalité téléphonique d'entreprise


![Icône Microsoft SharePoint.](media/Overview_of_Microsoft_Teams_image5.png)

-   Utilisée pour les sites et portails (par ex., actualité de l'entreprise, recherche et documentation de collaboration).

-   Implémente l'automatisation des processus métiers dans des bibliothèques de documents et listes d'informations en intégrant Microsoft Flow et PowerApps

-   Site d'équipe SharePoint puissant automatiquement fourni pour chaque équipe Microsoft Teams pour le stockage de fichiers, l'actualité de l'équipe, les pages, les listes, et plus encore.

-   Consultez [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](SharePoint-OneDrive-interact.md)

## <a name="teams-known-issuesknown-issuesmd"></a>[Problèmes connus dans Teams](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[Notes de publication du client Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a>Qu’est devenue la FAQ Microsoft Teams dédiée aux administrateurs ?

Bien que cette FAQ dédiée aux administrateurs ait été d’une grande aide lors du lancement de Microsoft Teams, c’est rapidement devenu un véritable « fourre-tout ». Nous avons donc décidé d’y mettre fin pour incorporer les précieuses informations qu’elle renfermait dans la présente documentation de Microsoft Teams. Vous retrouverez donc l’intégralité du contenu de la FAQ dans ce document, mais en contexte.

Si vous ne trouviez toutefois pas de réponse à vos questions, n’hésitez pas à nous en faire part via la section **Commentaires** ci-dessous. Nous ferons notre possible pour vous répondre sous 24 heures.

Par ailleurs, il existe **toujours** une FAQ relative à la [transition de Skype Entreprise vers Microsoft Teams](FAQ-journey.md). 
