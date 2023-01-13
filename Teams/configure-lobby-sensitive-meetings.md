---
title: Configurer la salle d’attente de réunion Microsoft Teams pour les réunions sensibles
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Découvrez comment configurer la salle d’attente des réunions Teams afin d’améliorer la sécurité des réunions sensibles à l’aide de stratégies d’administration, d’étiquettes de confidentialité et de modèles de réunion.
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800154"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>Configurer la salle d’attente de réunion Microsoft Teams pour les réunions sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

La salle d’attente de réunion est un outil que vous pouvez utiliser pour vous assurer que les personnes inappropriées ne sont pas admises aux réunions. En plaçant différents types de participants dans la salle d’attente, les organisateurs de la réunion peuvent les examiner et s’assurer qu’il est approprié pour eux d’assister à la réunion.

Par défaut, les personnes de votre organisation et [les invités](guest-access.md) sont admis directement aux réunions et les participants issus de domaines approuvés et de participants anonymes doivent attendre dans la salle d’attente pour être admis par un organisateur de réunion. Les organisateurs de réunion peuvent modifier ce paramètre par défaut pour chaque réunion qu’ils créent.

L’administrateur Teams peut contrôler la salle d’attente et d’autres paramètres associés à l’aide de stratégies de réunion, de modèles de réunion et d’étiquettes de confidentialité pour personnaliser l’expérience pour différents utilisateurs et différents types de réunions.

Le tableau suivant répertorie les fonctionnalités que vous pouvez utiliser pour gérer l’expérience de lobbying de votre organisation et où les configurer.

|Paramètres|Administration stratégie|Étiquette de confidentialité|Modèle|Organisateur de la réunion|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Annoncer quand les appelants entrants rejoignent ou quittent|Non|Non|Oui|Oui|
|Les utilisateurs anonymes et les appelants rendez-vous peuvent démarrer une réunion|Oui|Non|Non|Non|
|Les utilisateurs anonymes peuvent participer à une réunion|Oui|Non|Non|Non|
|Personnes la numérotation peut contourner la salle d’attente|Oui|Oui|Oui|Oui|
|Qui peut contourner la salle d’attente|Oui|Oui|Oui|Oui|

Pour plus d’informations sur l’utilisation des modèles et des étiquettes de confidentialité pour configurer les paramètres de réunion, consultez [Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md) et [Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings).

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

## <a name="lobby-settings-for-different-types-of-meetings"></a>Paramètres de salle d’attente pour différents types de réunions

Les paramètres suivants sont disponibles pour qui peut contourner la salle d’attente :

- Tout le monde
- Membres de mon organisation, organisations de confiance et invités
- Membres de mon organisation et invités
- Membres de mon organisation
- Personnes invités
- Organisateurs et co-organisateurs

Bien que l’organisateur de la réunion choisisse normalement le paramètre à utiliser pour chaque réunion, vous pouvez appliquer un paramètre particulier à l’aide d’un modèle de réunion ou d’une étiquette de confidentialité.

Si votre organisation exige que certains types de réunions ne soient pas suivis par des personnes extérieures à l’organisation, envisagez un modèle de réunion qui permet uniquement aux membres de votre organisation de contourner la salle d’attente. Cela garantit que les personnes extérieures à l’organisation qui ont été invitées ou envoyées accidentellement à un lien de réunion ne peuvent pas participer directement à la réunion.

Si votre organisation a des réunions où des informations très sensibles sont partagées et que vous devez être sûr que seules certaines personnes y participent, envisagez d’utiliser un modèle de réunion ou une étiquette de confidentialité qui permet uniquement aux organisateurs de la réunion de contourner la salle d’attente. Cela garantit que les organisateurs peuvent vérifier chaque participant entrant pour s’assurer qu’il doit être dans la réunion. Cela empêche également la réunion de démarrer jusqu’à ce qu’un organisateur rejoigne.

Pour les réunions sensibles en général, envisagez d’utiliser l’option **Personnes qui ont été invités**. Cela garantit que les personnes qui n’ont pas d’invitation à une réunion (y compris les invitations transférées) passent par la salle d’attente. (L’organisateur de la réunion peut également empêcher le transfert lorsqu’il crée la réunion.)

Pour plus d’informations sur l’utilisation de modèles de réunion et d’étiquettes de confidentialité, consultez [Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles](meeting-templates-sensitivity-labels-policies.md).

### <a name="attendees-calling-in-by-phone"></a>Participants appelant par téléphone

Par défaut, les participants qui composent par téléphone passent par la salle d’attente. Les administrateurs peuvent modifier cette valeur par défaut avec les **utilisateurs rendez-vous peuvent contourner la stratégie de réunion de l’administrateur de la salle d’attente** . Si vous souhaitez que ce paramètre soit activé ou désactivé, vous devez utiliser un modèle de réunion ou une étiquette de confidentialité.

Dans certains cas, vous souhaitez autoriser les appelants à contourner la salle d’attente, les organisateurs de la réunion peuvent contrôler ce paramètre, ou vous pouvez l’appliquer via un modèle de réunion ou une étiquette de confidentialité.

#### <a name="join-and-leave-notifications"></a>Joindre et quitter des notifications

Les organisateurs de la réunion ont la possibilité de faire en sorte que les participants appellent par téléphone lorsqu’ils rejoignent ou quittent une réunion. Si vous souhaitez vous assurer que les participants par téléphone sont annoncés pour certains types de réunions, vous pouvez appliquer ce paramètre avec un modèle de réunion.

## <a name="meeting-with-anonymous-participants"></a>Réunion avec des participants anonymes

Sauf si vous autorisez tout le monde à contourner la salle d’attente, les participants anonymes doivent passer par la salle d’attente pour assister à la réunion. Les organisateurs de la réunion peuvent alors décider si ces participants doivent être admis.

Si votre organisation n’autorise pas du tout les participants anonymes à participer à des réunions, vous pouvez désactiver le paramètre **Les utilisateurs anonymes peuvent rejoindre une réunion** dans le Centre d’administration Teams. Pour plus d’informations, consultez [Gérer les paramètres de réunion dans Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

Si vous avez certains groupes dans votre organisation (par exemple, le marketing) qui ont besoin d’organiser des réunions avec des participants anonymes et d’autres (comme la recherche) qui ne le devraient pas, vous pouvez utiliser des stratégies de réunion Teams pour configurer la participation anonyme à des réunions pour différents groupes. (Vous devez activer le paramètre **Les utilisateurs anonymes peuvent participer à une réunion** mentionnée ci-dessus pour que cela fonctionne.) Pour plus d’informations, consultez [Paramètres de stratégie de réunion - Participants & invités](/microsoftteams/meeting-policies-participants-and-guests).

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Gérer les conversations et les réunions externes dans Microsoft Teams](/microsoftteams/manage-external-access)
