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
ms.openlocfilehash: 0e6118e42600bda58bf7ddc9d7f8e0fee0b7ad9f
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706143"
---
# <a name="skype-for-business-online-retirement"></a>Déclassement de Skype Entreprise Online

Le 31 juillet 2021, Microsoft a mis hors service Skype Entreprise Online. Cette mise hors service a été annoncée en juillet 2019 pour donner aux clients un préavis de deux ans pour planifier leurs mises à niveau vers Microsoft Teams. Teams est l’application principale pour la communication et la collaboration dans Microsoft 365. Avec la mise hors service de Skype Entreprise Online, Microsoft veut s’assurer que les clients disposent des informations et des ressources nécessaires pour planifier et exécuter une mise à niveau vers Teams.  Le service consommateur Skype n’est pas affecté par cette mise hors service. Pour plus d’informations sur la raison pour laquelle Skype Entreprise Online a été mis hors service, consultez [faq : Mise à niveau de Skype Entreprise vers Microsoft Teams](FAQ-journey.yml).

Microsoft commencera à mettre hors service l’infrastructure Skype Entreprise Online le 30 juin 2022 ou après. En outre, à compter d’octobre 2022, Microsoft commencera à désactiver certains aspects de cette infrastructure propres aux organisations hybrides. Cet article contient des conseils pour les organisations avec des utilisateurs TeamsOnly qui ont été mis à niveau à partir de n’importe quelle version de Skype Entreprise.

> [!Important]
> **Le retrait de Skype Entreprise Online n’affecte pas la prise en charge des déploiements locaux de Skype Entreprise Server et Lync Server 2013**. Toutefois, les clients hybrides avec une combinaison d’utilisateurs hébergés en ligne et en local *doivent* mettre à niveau tous les utilisateurs *en ligne* pour qu’ils soient TeamsOnly. Le mode TeamsOnly doit être attribué à tous les utilisateurs en ligne à l’aide de TeamsUpgradePolicy. En outre, Microsoft fournit des mises à niveau assistées pour aider à automatiser la mise à niveau des utilisateurs en ligne restants Skype Entreprise en mode TeamsOnly. Les organisations hybrides n’ont pas besoin de déplacer leurs *utilisateurs Skype Entreprise locaux* vers le cloud à la suite de cette mise hors service. *Microsoft prend entièrement en charge les organisations hybrides avec un mélange d’utilisateurs TeamsOnly et d’utilisateurs Skype Entreprise locaux*. Les clients disposant de déploiements hybrides de Skype Entreprise Server ou Lync Server 2013 doivent examiner [les implications de la mise hors service de Skype Entreprise Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity.md#implications-of-the-upcoming-retirement-of-skype-for-business-online).


## <a name="what-to-expect-post-retirement"></a>À quoi s’attendre après la retraite ?

Il n’est plus possible pour les utilisateurs hébergés dans le cloud d’avoir un mode autre que TeamsOnly. Cela signifie :

 - Lorsque vous attribuez des licences aux nouveaux utilisateurs qui ne sont pas hébergés dans des Skype Entreprise Server locaux, le mode TeamsOnly est automatiquement attribué aux utilisateurs, quelle que soit la stratégie globale du locataire de TeamsUpgradePolicy.
 - Dans les organisations hybrides, lors du déplacement d’utilisateurs hébergés localement vers le cloud, le mode TeamsOnly est automatiquement attribué aux utilisateurs, que le `MoveToTeams` commutateur ait été spécifié dans `Move-CsUser`.
 - Les utilisateurs hébergés dans le cloud ne peuvent pas se faire attribuer un mode autre que TeamsOnly. Les utilisateurs hébergés en ligne n’utilisent *pas* Skype Entreprise serveur local.

Tous les clients qui ont des utilisateurs restants hébergés dans Skype Entreprise Online mais qui ne sont pas encore affectés au mode TeamsOnly doivent attribuer le mode TeamsOnly à ces utilisateurs dès que possible. En outre, Microsoft fournira des mises à niveau assistées pour les utilisateurs Skype Entreprise Online qui ne sont pas en mode TeamsOnly. L’expérience de mise à niveau assistée varie selon que votre organisation est une organisation en ligne pure ou une organisation avec des utilisateurs Skype Entreprise locaux. Pour plus d’informations, consultez [Mises à niveau assistées de Skype Entreprise Online vers Microsoft Teams](upgrade-assisted.md). Une fois la mise à niveau assistée terminée, tous les utilisateurs *en ligne* seront en mode TeamsOnly. *Tous les utilisateurs hébergés localement restent locaux et ne seront pas rendus TeamsOnly*.

Les utilisateurs en mode TeamsOnly reçoivent des conversations et des appels entrants dans Teams, et planifient également des réunions dans Teams. Ils ne peuvent pas lancer de conversations ou d’appels ou planifier des réunions dans Skype Entreprise Online. Les utilisateurs TeamsOnly peuvent participer Skype Entreprise réunions qu’ils ont déjà ou recevoir à l’avenir. Toutefois, une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online pour un utilisateur TeamsOnly donné, les utilisateurs TeamsOnly peuvent uniquement participer à Skype Entreprise réunions de manière anonyme.  À compter du 30 juin 2022, les utilisateurs TeamsOnly nouvellement créés ne seront plus approvisionnés avec l’infrastructure Skype Entreprise Online. Par conséquent, s’ils sont invités à une réunion Skype Entreprise, ils doivent participer anonymement. De même, les utilisateurs déplacés d’un site local vers Teams uniquement dans des organisations hybrides ne seront plus approvisionnés avec l’infrastructure Skype Entreprise Online à compter d’octobre 2022. Si ces utilisateurs sont invités à une réunion Skype Entreprise, ils doivent également participer de manière anonyme.


## <a name="guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Conseils pour les organisations avec des déploiements locaux de Skype Entreprise Server

 - Lorsque vous créez des utilisateurs dans votre environnement Active Directory local, si ces utilisateurs sont synchronisés avec Azure AD et que vous envisagez de les concéder sous licence pour Teams, *avant d’attribuer la licence à ces utilisateurs*, **vous devez d’abord les activer dans votre déploiement local Skype Entreprise et vous assurer que la modification a été synchronisée avec le cloud via Azure AD Connect**.  Vous pouvez vérifier que la modification est entièrement synchronisée avec le cloud à l’aide de Get-CsOnlineUser. La modification a été synchronisée si HostingProvider de l’utilisateur = « SRV: ».  Il ne doit pas être « sipfed.online.lync.com ».   

 - N’oubliez pas que les utilisateurs TeamsOnly devront participer anonymement à Skype Entreprise réunions une fois que Microsoft aura supprimé l’infrastructure Skype Entreprise Online héritée pour les organisations hybrides, à compter d’octobre 2022.  Pour plus d’informations, consultez [à quoi s’attendre après la retraite](#what-to-expect-post-retirement). En guise d’alternative, vous pouvez garantir que les réunions planifiées par tous les utilisateurs (qu’elles soient locales ou Teams uniquement) dans votre organisation sont des réunions Teams, ce qui permet la participation à une réunion authentifiée pour n’importe quel utilisateur de l’organisation (sous réserve de la configuration de la stratégie). Pour ce faire, effectuez les actions suivantes :
   - Pour tous les utilisateurs auxquels **Skype Entreprise uniquement** ou Skype Entreprise avec les modes **collaboration Teams**, remplacez le mode de coexistence **par Skype Entreprise avec collaboration teams et réunions**.  Ce mode offre les mêmes fonctionnalités que les deux autres, sauf que les nouvelles réunions planifiées par l’utilisateur seront des réunions Teams au lieu de réunions Skype Entreprise. Lorsque vous affectez ce mode directement à un utilisateur (par opposition au niveau du locataire), il convertit également automatiquement toutes les réunions Skype Entreprise en réunions Teams organisées par cet utilisateur.
   - Pour les utilisateurs qui sont en mode Îles, vous pouvez leur demander de toujours planifier des réunions dans Teams en leur affectant une instance de TeamsMeetingPolicy avec PreferredMeetingProviderForIslandsMode=Teams. 
   - Pour vous assurer que toutes les réunions Skype Entreprise existantes sont converties en réunions Teams (par exemple, si vous avez des utilisateurs Islands), vous pouvez utiliser Start-CsExMeetingMigration pour déclencher le [service de migration](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#trigger-meeting-migration-manually-via-powershell-cmdlet) de réunions pour convertir les réunions d’un utilisateur en Teams.
  

## <a name="actions-to-take-before-june-30-2022"></a>Actions à entreprendre avant le 30 juin 2022
Maintenant que Skype Entreprise Online est mis hors service, Microsoft commence à mettre hors service l’infrastructure de prise en charge au plus tôt le 30 juin 2022.  Pour toute organisation avec des utilisateurs TeamsOnly qui ont été mis à niveau à partir de n’importe quelle version de Skype Entreprise, vous devez prendre des mesures si l’une des situations suivantes s’applique :

- Si vous avez des utilisateurs TeamsOnly qui prévioulsy avaient des contacts dans Skype Entreprise *et* qui ne se sont pas encore connectés à Teams depuis la mise à niveau.
- Si vous avez des utilisateurs TeamsOnly qui ont encore Skype Entreprise réunions en ligne qu’ils ont organisées avant leur mise à niveau vers TeamsOnly.

Si l’une de ces situations s’applique à votre organisation, vous devez prendre des mesures avant le 30 juin 2022, comme décrit ci-dessous :

 - **Skype Entreprise Contacts en ligne :** une fois qu’un utilisateur a été mis à niveau vers le mode TeamsOnly, la première fois que l’utilisateur se connecte à Teams, tous les contacts existants dans le compte Skype Entreprise Online de cet utilisateur sont migrés vers Teams. Une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online, vous ne pouvez plus migrer les contacts *des utilisateurs qui ne se sont pas encore connectés à Teams.* Pour migrer des contacts de Skype Entreprise vers Teams, Microsoft recommande à tous les utilisateurs qui avaient précédemment Skype Entreprise se connecter à Teams au moins une fois avant le 30 juin 2022.

 - **Skype Entreprise réunions en ligne :** une fois qu’une organisation a été mise à niveau vers TeamsOnly, les utilisateurs créent toutes les nouvelles réunions en tant que réunions Teams. Dans certains cas, les utilisateurs TeamsOnly peuvent toujours avoir Skype Entreprise réunions en ligne qu’ils ont organisées précédemment. Actuellement, les utilisateurs TeamsOnly mis à niveau et les participants invités peuvent participer à ces réunions Skype Entreprise Online à l’aide de leur client Skype Entreprise. Une fois que Microsoft a supprimé l’infrastructure Skype Entreprise Online pour un utilisateur TeamsOnly donné, toutefois, cet utilisateur ne peut participer qu’aux réunions Skype Entreprise de manière anonyme, et les réunions Skype Entreprise Online *restantes organisées par cet utilisateur* n’existent plus. L’organisateur et les participants ne pourront pas participer à ces réunions. Si les utilisateurs des organisations TeamsOnly ont des réunions Skype Entreprise Online restantes qu’ils ont organisées, Microsoft recommande de replanifier ces réunions en tant que réunions Teams. Les administrateurs peuvent également utiliser le [service de migration](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) de réunions pour convertir ces réunions en réunions Teams. Dans les deux cas, effectuez ces actions avant le 30 juin 2022.  


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





