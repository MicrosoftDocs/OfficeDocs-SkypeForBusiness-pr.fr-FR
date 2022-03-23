---
title: Déclassement de Skype Entreprise Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Découvrez le plan de retrait d Skype Entreprise Online et comment Microsoft aide les clients à migrer vers Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f70378e2be1dd47126ee3d83009759c63643ae2f
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711758"
---
# <a name="skype-for-business-online-retirement"></a>Déclassement de Skype Entreprise Online

Le 31 juillet 2021, Microsoft a retiré Skype Entreprise Online. Cette retraite a été annoncée en juillet 2019 afin de donner aux clients deux ans d’avance pour planifier leurs mises à niveau vers Microsoft Teams. Teams est l’application principale pour la communication et la collaboration au Microsoft 365. Une fois Skype Entreprise Online mis à la retraite, Microsoft souhaite s’assurer que les clients disposent des informations et ressources requises pour planifier et exécuter une mise à niveau réussie vers Teams.  Le Skype grand public n’est pas affecté par cette retraite.

## <a name="why-is-skype-for-business-online-retiring"></a>Pourquoi est-Skype Entreprise la mise à la retraite en ligne ?

Depuis son introduction, Skype Entreprise Online est un outil précieux pour des millions de personnes dans le monde entier. En combinant la messagerie instantanée, les appels et la vidéo, vous Skype Entreprise online a établi de nouvelles possibilités pour les communications d’entreprise. Teams est le chapitre suivant de cette vision.  Les fonctionnalités des Microsoft Teams vont au-delà de celles d Skype Entreprise Online. L’innovation et le développement continus sur les plateformes Teams que les utilisateurs profitent de performances, fonctionnalités, flexibilité et sécurité plus riches. En regroupant les fonctionnalités suivantes dans une expérience unique, Teams de nouvelles façons de travailler :

- Conversation
- Vidéo
- Appel
- Collaboration sur les documents
- Intégration de l’application

Teams est bien plus qu’une mise à niveau Skype Entreprise Online. Il s’agit d’un outil puissant qui permet aux établissements scolaires et aux organisations de devenir plus agiles et d’améliorer l’efficacité des flux de travail clés. Pour plus d’informations sur les avantages Teams’utilisation de cette Teams, le livre [blanc Sur l’impact™ économique total d’Microsoft Teams](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1).

## <a name="organizations-with-skype-for-business-online"></a>Organisations avec Skype Entreprise Online

Microsoft fournit un processus de mise à niveau assisté pour aider les organisations à déplacer les utilisateurs Skype Entreprise Online vers Teams uniquement. Teams est disponible dans la plupart des plans Microsoft 365 Entreprise et Enterprise, et les investissements en gestion des licences existants avancent à Teams. Les fonctionnalités qui constituent actuellement des charges de travail Premium dans Skype Entreprise Online continueront de l’être dans Teams. Par exemple, si vous avez acheté l’audioconférence autonome ou dans le cadre d’une offre E5 avec Skype Entreprise, l’audioconférence sera activée dans Teams.

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisations avec déploiements locaux d’Skype Entreprise Server

L’retrait d Skype Entreprise Online n’affecte pas la prise en charge des déploiements locaux d’Skype Entreprise Server et de Lync Server 2013. Toutefois, les clients hybrides bordant un mélange d’utilisateurs homed online et sur site doivent mettre à niveau les *utilisateurs en* ligne. Ces utilisateurs en ligne doivent être affectés Teams mode Uniquement à l’aide de TeamsUpgradePolicy. Microsoft fournit des mises à niveau assistées pour aider à automatiser la mise à niveau des utilisateurs Skype Entreprise Online vers Teams mode uniquement. Les organisations hybrides n’ont pas besoin de déplacer leurs *utilisateurs* Skype Entreprise dans le cloud suite à cette retraite. Microsoft prend entièrement en charge les organisations hybrides qui utilisent un mélange Teams seuls les utilisateurs et les utilisateurs Skype Entreprise site. Les clients ayant des déploiements hybrides Skype Entreprise Server Lync Server 2013 doivent examiner les [implications](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online) de la mise sous Skype Entreprise Online.

## <a name="what-to-expect-post-retirement"></a>Ce à quoi vous pouvez vous attendre après la retraite

Il n’est plus possible pour les utilisateurs homed in the cloud de se voir attribuer un mode autre que TeamsOnly. Cela signifie que :
 - Lors de l’attribution de licences à de nouveaux utilisateurs (à l’exception des utilisateurs homed in local Skype Entreprise Server), les utilisateurs se verront automatiquement attribuer le mode TeamsOnly, quelle que soit la stratégie globale du client de TeamsUpgradePolicy.
 - Dans les organisations hybrides, lors du déplacement d’utilisateurs homed local vers le cloud, les utilisateurs se voit automatiquement attribuer le mode TeamsOnly (`MoveToTeams``Move-CsUser`spécifier si le commutateur a été spécifié dans .)
 - Les utilisateurs do accueil dans le cloud (par exemple, n’utilisent pas Skype Entreprise sur site) ne peuvent pas se voir attribuer un mode autre que Teams Uniquement.

Les clients peuvent avoir une partie restante de leur population d’utilisateurs, qui sont Skype Entreprise Online et qui ne sont pas encore affectés Teams mode Uniquement.  Les clients doivent attribuer Teams mode uniquement à ces utilisateurs dès que possible.  En outre, Microsoft proposera des mises à niveau assistées pour les utilisateurs Skype Entreprise Online qui ne sont pas en Teams mode uniquement.  L’expérience de mise à niveau assistée varie selon que votre organisation est une organisation en ligne entière ou une organisation avec des utilisateurs Skype Entreprise site.  Pour plus d’informations, [voir Mises à niveau assistées d Skype Entreprise Online vers Microsoft Teams](upgrade-assisted.md).

Une fois la mise à niveau assistée terminée,  tous les utilisateurs en ligne sont en Teams mode Uniquement. Les utilisateurs Teams mode uniquement reçoivent les conversations et appels entrants dans Teams et peuvent également planifier des réunions dans Teams. Ils ne peuvent pas démarrer de conversations ou d’appels, ni planifier de réunions dans Skype Entreprise Online.  Toutefois, Teams seuls les utilisateurs peuvent Skype Entreprise les réunions qu’ils ont ou reçoivent déjà. Enfin, *tous les utilisateurs* dont le domicile est local restent sur site et ne sont pas Teams uniquement.


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Comment Microsoft aide les clients à mettre à niveau vers Teams

Nous vous recommandons vivement de commencer la mise à niveau de Skype Entreprise Online vers Teams dès aujourd’hui.

Tirez parti des ressources disponibles pour planifier votre déploiement Teams mise à niveau à partir d’Skype Entreprise :

- [Teams documentation relative au déploiement et à la mise à niveau](upgrade-start-here.md) – Conseils techniques gratuits pour les administrateurs informatiques.

- [Teams ateliers](./upgrade-workshops-landing-page.yml) de planification de la mise à niveau – Ateliers de planification de mise à niveau interactifs gratuits où vous recevrez des conseils, des recommandations et des ressources destinées à vous aider à planifier et à implémenter votre mise à niveau vers Teams.

- [Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams –](upgrade-assisted.md) Programme automatisé qui vous aide à mettre à niveau Skype Entreprise utilisateurs Online vers Teams.

- [FastTrack pour Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams assistance au déploiement disponible pour les plans éligibles.

- [Teams formation en direct](./instructor-led-training-teams-landing-page.yml) – Cours de formation en ligne gratuits conçus pour aider votre organisation à fonctionner avec Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) : ateliers en ligne gratuits pour professionnels de l’informatique et décideurs qui décrivent les meilleures pratiques pour des scénarios clés dans Teams.

- [Partenaires Microsoft](https://www.microsoft.com/solution-providers/home) : les fournisseurs de solutions Microsoft peuvent vous aider à tirer pleinement parti de Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams actualités sur les nouvelles fonctionnalités, les ressources d’adoption et d’utilisation, les appareils Teams et l’intégration à d’autres applications professionnelles.

Si vous êtes un client Skype Entreprise Online, commencez à planifier votre mise à niveau vers Teams aujourd’hui. Nous sommes ravis de vous faire découvrir ses puissantes fonctionnalités de communication et de collaboration, et nous nous engageons à vous aider tout au long du chemin.  Pour plus d’informations sur Skype Entreprise retrait en ligne, voir FAQ — Mise à niveau d’Skype Entreprise [à Microsoft Teams](FAQ-journey.yml).





