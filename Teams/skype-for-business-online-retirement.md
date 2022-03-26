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
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783903"
---
# <a name="skype-for-business-online-retirement"></a>Déclassement de Skype Entreprise Online

Le 31 juillet 2021, Microsoft a retiré Skype Entreprise Online. Cette retraite a été annoncée en juillet 2019 afin de donner aux clients deux ans d’avance pour planifier leurs mises à niveau vers Microsoft Teams. Teams est l’application principale pour la communication et la collaboration au Microsoft 365. Une fois Skype Entreprise Online mis à la retraite, Microsoft souhaite s’assurer que les clients disposent des informations et ressources requises pour planifier et exécuter une mise à niveau réussie vers Teams.  Le Skype grand public n’est pas affecté par cette retraite. Pour savoir pourquoi Skype Entreprise Online a été retiré, voir FAQ : mise à niveau [d’Skype Entreprise à Microsoft Teams](FAQ-journey.yml).

Microsoft commencera à désaffecter l’infrastructure Skype Entreprise Online le 30 juin 2022 ou après. Cet article contient des conseils pour les organisations qui utilisent TeamsOnly et qui ont été mises à niveau à partir de n’importe quelle version Skype Entreprise.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisations avec déploiements locaux d’Skype Entreprise Server

L’retrait d Skype Entreprise Online n’affecte pas la prise en charge des déploiements locaux d’Skype Entreprise Server et de Lync Server 2013. Toutefois, les clients hybrides bordant un mélange d’utilisateurs homed online et sur site doivent mettre à niveau les *utilisateurs en* ligne. Tous les utilisateurs en ligne doivent avoir le mode TeamsOnly à l’aide de TeamsUpgradePolicy. Microsoft fournit des mises à niveau assistées pour vous aider à automatiser la mise à niveau des utilisateurs Skype Entreprise Online restants en mode TeamsOnly. Les organisations hybrides n’ont pas besoin de déplacer leurs *utilisateurs* Skype Entreprise vers le cloud suite à cette retraite. Microsoft prend entièrement en charge les organisations hybrides qui utilisent un mélange d’utilisateurs De TeamsOnly et d’utilisateurs Skype Entreprise site. Les clients ayant des déploiements hybrides Skype Entreprise Server ou Lync Server 2013 devraient consulter l’évaluation du retrait d [Skype Entreprise Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Ce à quoi vous pouvez vous attendre après la retraite

Il n’est plus possible pour les utilisateurs homed in the cloud de se voir attribuer un mode autre que TeamsOnly. Cela signifie que :

 - Lors de la gestion des licences de nouveaux utilisateurs non Skype Entreprise Server locaux, les utilisateurs sont automatiquement affectés au mode TeamsOnly, quelle que soit la stratégie globale du client de TeamsUpgradePolicy.
 - Dans les organisations hybrides, lors du déplacement d’utilisateurs homed local vers le cloud, les utilisateurs se voit automatiquement attribuer le mode `MoveToTeams` TeamsOnly, que le commutateur soit ou non spécifié `Move-CsUser`.
 - Les utilisateurs homed in the cloud ne peuvent pas se voir attribuer un mode autre que TeamsOnly. Les utilisateurs do accueil en ligne *n’utilisent* Skype Entreprise serveur local.

Les clients peuvent avoir des utilisateurs restants Skype Entreprise Online et qui ne sont pas encore affectés au mode TeamsOnly. Les clients doivent attribuer le mode TeamsOnly à ces utilisateurs dès que possible. Microsoft proposera des mises à niveau assistées pour les Skype Entreprise Online qui ne sont pas en mode TeamsOnly. L’expérience de mise à niveau assistée varie selon que votre organisation est une organisation en ligne entière ou une organisation avec des utilisateurs Skype Entreprise site. Pour plus d’informations, [voir Mises à niveau assistées d Skype Entreprise Online vers Microsoft Teams](upgrade-assisted.md).

Une fois la mise à niveau assistée terminée *, tous les* utilisateurs en ligne seront en mode TeamsOnly. Les utilisateurs en mode TeamsOnly reçoivent les conversations et appels entrants dans Teams et peuvent également planifier des réunions dans Teams. Ils ne peuvent pas démarrer de conversations ou d’appels, ni planifier de réunions dans Skype Entreprise Online.  Toutefois, les utilisateurs de TeamsOnly peuvent Skype Entreprise les réunions qu’ils ont ou reçoivent déjà. Enfin, tous les utilisateurs dont le domicile est local restent sur site et ne *seront pas faits TeamsOnly*.

## <a name="actions-to-take-before-june-30-2022"></a>Actions à prendre avant le 30 juin 2022
À présent que Skype Entreprise Online est supprimé, Microsoft commencera à désaffecter l’infrastructure de prise en charge au plus tôt le 30 juin 2022.  Pour toute organisation avec des utilisateurs TeamsOnly mis à niveau à partir de n’importe quelle version de Skype Entreprise, vous devez prendre des mesures si l’une de ces situations s’applique :

- Si vous avez des utilisateurs de TeamsOnly qui prévioulaient des contacts dans Skype Entreprise et qui ne  se sont pas encore connectés à Teams depuis la mise à niveau.
- Si des utilisateurs de TeamsOnly ont encore Skype Entreprise Online qu’ils ont organisées avant leur mise à niveau vers TeamsOnly.

Si l’une de ces situations s’applique à votre organisation, vous devez prendre des mesures avant le 30 juin 2022, comme décrit ci-dessous :

 - **Skype Entreprise Contacts** en ligne : une fois qu’un utilisateur a été mis à niveau en mode TeamsOnly, la première fois qu’il se connecte à Teams, tous les contacts existants dans le compte Skype Entreprise Online de cet utilisateur sont migrés vers Teams. Une fois l’infrastructure Skype Entreprise Online supprimée, vous ne pouvez plus migrer les contacts des utilisateurs qui ne se sont pas encore connectés *à Teams.* Pour migrer des contacts d’Skype Entreprise vers Teams, Microsoft recommande à tous les utilisateurs qui avaient précédemment Skype Entreprise de se connecter à Teams au moins une fois avant le 30 juin 2022.

 - **Skype Entreprise Réunions** en ligne : après la mise à niveau d’une organisation vers TeamsOnly, les utilisateurs créent toutes les réunions sous la forme Teams réunions. Dans certains cas, il est possible que les utilisateurs de TeamsOnly Skype Entreprise des réunions en ligne qu’ils ont précédemment organisées. Actuellement, les utilisateurs de TeamsOnly mis à niveau et les participants invités peuvent participer à Skype Entreprise réunions en ligne à l’aide Skype Entreprise client client. Après la suppression de l’infrastructure Skype Entreprise Online pour un utilisateur TeamsOnly donné, toutefois, les réunions Skype Entreprise Online restantes organisées par cet utilisateur n’existeront plus. L’organisateur et les participants ne pourront pas participer à ces réunions. Si les utilisateurs des organisations TeamsOnly ont des réunions Skype Entreprise Online qu’ils ont organisées, Microsoft recommande de reprogrammer ces réunions en tant que réunions Teams réunion. Les administrateurs peuvent également utiliser le [Service de migration](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) de réunions pour convertir ces réunions en réunions Teams réunion. Dans les deux cas, terminez ces actions avant le 30 juin 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Comment Microsoft aide les clients à mettre à niveau vers Teams

Nous vous recommandons vivement de commencer la mise à niveau de Skype Entreprise Online vers Teams dès aujourd’hui. Tirez parti des ressources disponibles pour planifier votre déploiement Teams mise à niveau à partir d’Skype Entreprise :

- [Teams documentation relative au déploiement et à la mise à niveau](upgrade-start-here.md) – Conseils techniques gratuits pour les administrateurs informatiques.

- [Teams ateliers](./upgrade-workshops-landing-page.yml) de planification de la mise à niveau – Ateliers de planification de mise à niveau interactifs gratuits où vous recevrez des conseils, des recommandations et des ressources destinées à vous aider à planifier et à implémenter votre mise à niveau vers Teams.

- [Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams –](upgrade-assisted.md) Programme automatisé qui vous aide à mettre à niveau Skype Entreprise utilisateurs Online vers Teams.

- [FastTrack pour Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams assistance au déploiement disponible pour les plans éligibles.

- [Teams formation en direct](./instructor-led-training-teams-landing-page.yml) – Cours de formation en ligne gratuits conçus pour aider votre organisation à fonctionner avec Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) : ateliers en ligne gratuits pour professionnels de l’informatique et décideurs qui décrivent les meilleures pratiques pour des scénarios clés dans Teams.

- [Partenaires Microsoft](https://www.microsoft.com/solution-providers/home) : les fournisseurs de solutions Microsoft peuvent vous aider à tirer pleinement parti de Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Teams actualités sur les nouvelles fonctionnalités, les ressources d’adoption et d’utilisation, les appareils Teams et l’intégration à d’autres applications professionnelles.

Si vous êtes un client Skype Entreprise Online, commencez à planifier votre mise à niveau vers Teams aujourd’hui. Nous sommes ravis de vous faire découvrir ses puissantes fonctionnalités de communication et de collaboration, et nous nous engageons à vous aider tout au long du chemin.  Pour plus d’informations sur Skype Entreprise retrait en ligne, voir [FAQ —](FAQ-journey.yml) Mise à niveau de Skype Entreprise à Microsoft Teams.





