---
title: Déclassement de Skype Entreprise Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Découvrez le plan de retraite de Skype Entreprise Online et comment Microsoft aide les clients à migrer vers Teams.
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
ms.openlocfilehash: 13d7032c78a7863b46bb186553b0b67e67f8c626
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494491"
---
# <a name="skype-for-business-online-retirement"></a>Déclassement de Skype Entreprise Online

Le 31 juillet 2021, Microsoft a mis hors service Skype Entreprise Online. Cette mise hors service a été annoncée en juillet 2019 pour donner aux clients un préavis de deux ans pour planifier leurs mises à niveau vers Microsoft Teams. Teams est l’application principale pour la communication et la collaboration dans Microsoft 365. Avec la mise hors service de Skype Entreprise Online, Microsoft veut s’assurer que les clients disposent des informations et des ressources nécessaires pour planifier et exécuter une mise à niveau vers Teams.  Le service consommateur Skype n’est pas affecté par cette mise hors service. Pour plus d’informations sur la raison pour laquelle Skype Entreprise Online a été mis hors service, consultez [faq : Mise à niveau de Skype Entreprise vers Microsoft Teams](FAQ-journey.yml).

Microsoft commencera à mettre hors service l’infrastructure Skype Entreprise Online le 30 juin 2022 ou après. Cet article contient des conseils pour les organisations avec des utilisateurs TeamsOnly qui ont été mis à niveau à partir de n’importe quelle version de Skype Entreprise.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organisations avec des déploiements locaux de Skype Entreprise Server

La mise hors service de Skype Entreprise Online n’affecte pas la prise en charge des déploiements locaux de Skype Entreprise Server et de Lync Server 2013. Toutefois, les clients hybrides avec une combinaison d’utilisateurs hébergés en ligne et en local doivent mettre à niveau tous les utilisateurs *en ligne* . Le mode TeamsOnly doit être attribué à tous les utilisateurs en ligne à l’aide de TeamsUpgradePolicy. Microsoft fournit des mises à niveau assistées pour aider à automatiser la mise à niveau des utilisateurs restants Skype Entreprise Online vers le mode TeamsOnly. Les organisations hybrides n’ont pas besoin de déplacer leurs *utilisateurs Skype Entreprise locaux* vers le cloud à la suite de cette mise hors service. Microsoft prend entièrement en charge les organisations hybrides avec un mélange d’utilisateurs TeamsOnly et d’utilisateurs Skype Entreprise locaux. Les clients disposant de déploiements hybrides de Skype Entreprise Server ou Lync Server 2013 doivent passer en revue [la mise hors service de Skype Entreprise Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

Lorsque vous créez des utilisateurs dans votre environnement Active Directory local, si ces utilisateurs sont synchronisés avec Azure AD et que vous envisagez de les concéder sous licence pour Teams, *avant d’attribuer la licence à ces utilisateurs*, **vous devez d’abord les activer dans votre déploiement local Skype Entreprise et vous assurer que la modification a été synchronisée avec le cloud via Azure AD Connect**.  Vous pouvez vérifier que la modification est entièrement synchronisée avec le cloud à l’aide de Get-CsOnlineUser. La modification a été synchronisée si HostingProvider de l’utilisateur = « SRV: ».  Il ne doit pas être « sipfed.online.lync.com ».   

## <a name="what-to-expect-post-retirement"></a>À quoi s’attendre après la retraite ?

Il n’est plus possible pour les utilisateurs hébergés dans le cloud d’avoir un mode autre que TeamsOnly. Cela signifie :

 - Lorsque vous attribuez des licences aux nouveaux utilisateurs qui ne sont pas hébergés dans des Skype Entreprise Server locaux, le mode TeamsOnly est automatiquement attribué aux utilisateurs, quelle que soit la stratégie globale du locataire de TeamsUpgradePolicy.
 - Dans les organisations hybrides, lors du déplacement d’utilisateurs hébergés localement vers le cloud, le mode TeamsOnly est automatiquement attribué aux utilisateurs, que le `MoveToTeams` commutateur ait été spécifié dans `Move-CsUser`.
 - Les utilisateurs hébergés dans le cloud ne peuvent pas se faire attribuer un mode autre que TeamsOnly. Les utilisateurs hébergés en ligne n’utilisent *pas* Skype Entreprise serveur local.

Les clients peuvent avoir des utilisateurs restants hébergés dans Skype Entreprise Online et qui ne sont pas encore affectés au mode TeamsOnly. Les clients doivent attribuer le mode TeamsOnly à ces utilisateurs dès que possible. Microsoft fournira des mises à niveau assistées pour les utilisateurs Skype Entreprise Online qui ne sont pas en mode TeamsOnly. L’expérience de mise à niveau assistée varie selon que votre organisation est une organisation en ligne pure ou une organisation avec des utilisateurs Skype Entreprise locaux. Pour plus d’informations, consultez [Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams](upgrade-assisted.md).

Une fois la mise à niveau assistée terminée, tous les utilisateurs *en ligne* seront en mode TeamsOnly. Les utilisateurs en mode TeamsOnly reçoivent des conversations et des appels entrants dans Teams, et planifient également des réunions dans Teams. Ils ne peuvent pas lancer de conversations ou d’appels ou planifier des réunions dans Skype Entreprise Online.  Toutefois, les utilisateurs TeamsOnly peuvent participer à Skype Entreprise réunions qu’ils ont déjà ou qu’ils recevront à l’avenir. Enfin, *tous les utilisateurs hébergés localement restent locaux et ne seront pas rendus TeamsOnly*.

## <a name="actions-to-take-before-june-30-2022"></a>Actions à entreprendre avant le 30 juin 2022
Maintenant que Skype Entreprise Online est mis hors service, Microsoft commence à mettre hors service l’infrastructure de prise en charge au plus tôt le 30 juin 2022.  Pour toute organisation avec des utilisateurs TeamsOnly qui ont été mis à niveau à partir de n’importe quelle version de Skype Entreprise, vous devez prendre des mesures si l’une des situations suivantes s’applique :

- Si vous avez des utilisateurs TeamsOnly qui prévioulsy avaient des contacts dans Skype Entreprise *et* qui ne se sont pas encore connectés à Teams depuis la mise à niveau.
- Si vous avez des utilisateurs TeamsOnly qui ont encore Skype Entreprise réunions en ligne qu’ils ont organisées avant leur mise à niveau vers TeamsOnly.

Si l’une de ces situations s’applique à votre organisation, vous devez prendre des mesures avant le 30 juin 2022, comme décrit ci-dessous :

 - **Skype Entreprise Contacts en ligne :** une fois qu’un utilisateur a été mis à niveau vers le mode TeamsOnly, la première fois que l’utilisateur se connecte à Teams, tous les contacts existants dans le compte Skype Entreprise Online de cet utilisateur sont migrés vers Teams. Une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online, vous ne pouvez plus migrer les contacts *des utilisateurs qui ne se sont pas encore connectés à Teams.* Pour migrer des contacts de Skype Entreprise vers Teams, Microsoft recommande à tous les utilisateurs qui avaient précédemment Skype Entreprise se connecter à Teams au moins une fois avant le 30 juin 2022.

 - **Skype Entreprise réunions en ligne :** une fois qu’une organisation a été mise à niveau vers TeamsOnly, les utilisateurs créent toutes les nouvelles réunions en tant que réunions Teams. Dans certains cas, les utilisateurs TeamsOnly peuvent toujours avoir Skype Entreprise réunions en ligne qu’ils ont organisées précédemment. Actuellement, les utilisateurs TeamsOnly mis à niveau et les participants invités peuvent participer à ces réunions Skype Entreprise Online à l’aide de leur client Skype Entreprise. Une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online pour un utilisateur TeamsOnly donné, toutefois, les réunions Skype Entreprise Online restantes organisées par cet utilisateur n’existeront plus. L’organisateur et les participants ne pourront pas participer à ces réunions. Si les utilisateurs des organisations TeamsOnly ont des réunions Skype Entreprise Online restantes qu’ils ont organisées, Microsoft recommande de replanifier ces réunions en tant que réunions Teams. Les administrateurs peuvent également utiliser le [service de migration](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) de réunions pour convertir ces réunions en réunions Teams. Dans les deux cas, effectuez ces actions avant le 30 juin 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Comment Microsoft aide les clients à effectuer une mise à niveau vers Teams

Nous vous recommandons vivement de commencer votre mise à niveau de Skype Entreprise Online vers Teams dès aujourd’hui. Tirez parti des ressources disponibles pour planifier le déploiement et la mise à niveau de Teams à partir de Skype Entreprise :

- [Documentation sur le déploiement et la mise à niveau](upgrade-start-here.md) teams – Conseils techniques gratuits pour les administrateurs informatiques.

- [Ateliers de planification de la mise à niveau Teams : ateliers gratuits](./upgrade-workshops-landing-page.yml) de planification de la mise à niveau interactive, où vous recevrez des conseils, des bonnes pratiques et des ressources conçues pour vous aider à planifier et à implémenter votre mise à niveau vers Teams.

- [Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams](upgrade-assisted.md) – Programme automatisé qui vous aide à mettre à niveau des utilisateurs Skype Entreprise Online vers Teams.

- Aide au déploiement [de FastTrack pour Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) – Teams disponible pour les plans éligibles.

- [Formation en direct Teams](./instructor-led-training-teams-landing-page.yml) : classes de formation en ligne gratuites conçues pour permettre à votre organisation de fonctionner avec Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) – Ateliers en ligne gratuits pour les professionnels de l’informatique et les décideurs qui décrivent les meilleures pratiques pour les scénarios clés dans Teams.

- [Partenaires Microsoft](https://www.microsoft.com/solution-providers/home) – Les fournisseurs de solutions Microsoft peuvent vous aider à tirer pleinement parti de Teams.

- [Blog Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – Actualités Teams sur les nouvelles fonctionnalités, les ressources d’adoption et d’utilisation, les appareils Teams et l’intégration avec d’autres applications métier.

Si vous êtes actuellement un client Skype Entreprise Online, commencez à planifier votre mise à niveau vers Teams dès aujourd’hui. Nous sommes ravis que vous ayez l’expérience de ses puissantes fonctionnalités de communication et de collaboration, et nous nous engageons à vous aider tout au long du processus.  Pour plus d’informations sur la mise hors service Skype Entreprise Online, consultez [faq : Mise à niveau de Skype Entreprise vers Microsoft Teams](FAQ-journey.yml).





