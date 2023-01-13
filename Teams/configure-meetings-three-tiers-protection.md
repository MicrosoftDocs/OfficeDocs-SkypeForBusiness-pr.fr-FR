---
title: Configurer des réunions Teams avec trois niveaux de protection
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
- m365solution-overview
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Découvrez comment configurer des réunions Teams pour une meilleure sécurité à l’aide de trois niveaux de protection, en équilibrant sécurité et facilité de collaboration.
ms.openlocfilehash: 607c4d484df714fd4fba736ffd618aafdbab67d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800134"
---
# <a name="configure-teams-meetings-with-three-tiers-of-protection"></a>Configurer des réunions Teams avec trois niveaux de protection

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Les articles de cette série fournissent des options d’utilisation des fonctionnalités de conformité disponibles dans Teams et Microsoft 365 pour créer un environnement de réunion qui répond à vos exigences de conformité. Nous allons examiner les options disponibles avec les étiquettes de confidentialité et les modèles et comment vous pouvez les utiliser avec d’autres paramètres d’administration Teams.

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

Cet article définit quatre configurations différentes, en commençant par une configuration de base pour les réunions qui n’ont pas d’exigences de conformité spécifiques. Chaque configuration supplémentaire représente une augmentation significative de la protection à mesure que les options de réunion deviennent plus restreintes. Les configurations de cet article fournissent des exemples de configuration de la protection pour les réunions avec différents niveaux de sensibilité. Utilisez ces exemples pour comprendre ce qui est possible et modifier les paramètres spécifiques en fonction des besoins de votre organisation.

Nous allons aborder ces trois configurations :

- Protection de la base de référence

- Protection sensible

- Protection hautement sensible

En outre, nous allons aborder une variante de la configuration hautement sensible conçue pour les présentations qui ont une interaction minimale de la part des participants.

## <a name="three-tiers-at-a-glance"></a>Trois niveaux en un coup d’œil

Le tableau suivant récapitule les configurations pour chaque niveau. Utilisez ces configurations comme recommandations de point de départ et ajustez les configurations pour répondre aux besoins de votre organisation. Selon vos besoins en matière de conformité, vous n’avez peut-être pas besoin de tous les niveaux.

|&nbsp;|Base|Sensible|Très sensible|Présentation très sensible|
|:-----|:-----|:-----|:-----|:-----|
|Autoriser la caméra pour les participants|**Activé**|**Activé**|**Activé**|**Désactivé**|
|Autoriser le micro pour les participants|**Activé**|**Activé**|**Activé**|**Désactivé**|
|Appliquer un filigrane au flux vidéo de tout le monde|**Désactivé**|**Désactivé**|**Activé**|**Activé**|
|Appliquer un filigrane au contenu partagé|**Désactivé**|**Désactivé**|**Activé**|**Activé**|
|Chiffrement de bout en bout|**Désactivé**|**Désactivé**|**Activé**|**Activé**|
|Gérer ce que voient les participants|**Désactivé**|**Activé**|**Activé**|**Activé**|
|Conversation de réunion|**Activé**|**Activé**|**En réunion uniquement**|**Désactivé**|
|Personnes la numérotation peut contourner la salle d’attente|**Désactivé**|**Désactivé**|**Désactivé**|**Désactivé**|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|**Désactivé**|**Désactivé**|**Activé**|**Activé**|
|Enregistrer automatiquement|**Désactivé**|**Désactivé**|**Désactivé**|**Désactivé**|
|Qui peut contourner la salle d’attente|**Personnes dans mon organisation, les personnes dans les domaines de confiance et les invités**|**Personnes j’invite**|**Seulement moi et les co-organisateurs**|**Seulement moi et les co-organisateurs**|
|Qui peut présenter|**Membres de mon organisation et invités**|**Membres de mon organisation et invités**|**Seuls les organisateurs et les co-organisateurs**|**Seuls les organisateurs et les co-organisateurs**|
|Qui peut enregistrer|**Organisateurs et présentateurs**|**Organisateurs et co-organisateurs**|Désactivé en raison d’un filigrane|Désactivé en raison d’un filigrane|

Pour plus d’informations sur la configuration de chaque niveau, consultez :

- [Configurer des réunions Teams avec la protection de base](configure-meetings-baseline-protection.md)
- [Configurer des réunions Teams avec protection pour les données sensibles](configure-meetings-sensitive-protection.md)
- [Configurer des réunions Teams avec protection pour les données hautement sensibles](configure-meetings-highly-sensitive-protection.md)

## <a name="managing-compliance-with-sensitivity-labels-and-meeting-templates"></a>Gestion de la conformité avec les étiquettes de confidentialité et les modèles de réunion

Les modèles de réunion et les étiquettes de confidentialité ont la possibilité d’appliquer certains paramètres de réunion. La plupart des paramètres peuvent être appliqués comme activés ou désactivés ou peuvent être laissés non configurés afin que l’organisateur de la réunion puisse les définir.

> [!Important]
> Certaines fonctionnalités sont [contrôlées par des stratégies d’administration](meeting-templates-sensitivity-labels-policies.md#policies-labels-templates-and-meetings-settings) et doivent y être activées avant de pouvoir être contrôlées par des modèles de réunion et des étiquettes de confidentialité.

Certains paramètres sont uniquement disponibles dans les étiquettes de confidentialité et d’autres uniquement dans les modèles. Plusieurs sont disponibles dans les deux :

- Conversation
- Chiffrement de bout en bout
- Paramètres de la salle d’attente
- Enregistrement de réunion
- Tatouage

Les étiquettes et les modèles de confidentialité peuvent être utilisés ensemble pour vous aider à répondre à vos besoins de conformité. Pour plus d’informations, consultez [Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble](meeting-templates-sensitivity-labels-policies.md).

## <a name="meeting-chat"></a>Conversation de réunion

La conversation de réunion peut être une partie importante de la collaboration pendant une réunion. Toutefois, vous souhaiterez peut-être limiter les conversations de réunion dans certains types de réunions pour éviter que des informations sensibles y soient partagées.

En tant qu’administrateur, vous pouvez contrôler la conversation de réunion des manières suivantes :

- **La stratégie de réunion d’administration Teams** (par utilisateur ou groupe) peut être utilisée pour autoriser la conversation, autoriser la conversation pour tout le monde, sauf les participants anonymes, ou désactiver la conversation.
- **Le paramètre d’étiquette de confidentialité** (par réunion) peut imposer que la conversation soit activée ou désactivée ou autorisée uniquement pendant la réunion. Ce paramètre peut être laissé non configuré pour être contrôlé par un modèle ou l’organisateur de la réunion.
- **Le paramètre de modèle** de réunion (par réunion) peut imposer que la conversation soit activée ou désactivée ou autorisée uniquement pendant la réunion. Ce paramètre peut être laissé non configuré pour être contrôlé par l’organisateur de la réunion.

Pour les trois niveaux de protection, nous autorisons la conversation pour les réunions de base et sensibles et nous la limitons aux réunions très sensibles uniquement en réunion.

Pour plus d’informations, consultez [Gérer la conversation pour les réunions Teams sensibles](manage-chat-sensitive-meetings.md).

## <a name="meeting-recordings"></a>Enregistrements de réunion

En tant qu’administrateur, vous pouvez contrôler les enregistrements de réunion des manières suivantes :

- Stratégie de réunion **d’administrateur d’enregistrement** cloud (par utilisateur ou groupe)
- La stratégie de réunion administrateur **Réunions expire automatiquement** (enregistrement de la suppression) (par utilisateur ou groupe)
- Paramètre **Qui peut enregistrer** dans les étiquettes de confidentialité et les modèles de réunion (par réunion)
- Paramètre **Enregistrement automatiquement** dans les étiquettes de confidentialité et les modèles de réunion (par réunion)

Si votre organisation ou certaines personnes ou groupes au sein de celle-ci ne doivent jamais être en mesure d’enregistrer des réunions, vous pouvez désactiver la fonctionnalité à l’aide de la stratégie de réunion **d’administrateur d’enregistrement cloud** .

Si certains types de réunions doivent toujours être enregistrés, vous pouvez appliquer le paramètre **Enregistrement automatiquement** à l’aide d’un modèle de réunion ou d’une étiquette de confidentialité.

Dans les trois niveaux abordés ici, l’enregistrement est désactivé dans les réunions très sensibles, car nous utilisons un chiffrement de bout en bout et des filigranes sur le contenu partagé et la vidéo. Si vous devez être en mesure d’enregistrer des réunions très sensibles, veillez à ne pas appliquer de filigranes ou de chiffrement de bout en bout avec l’étiquette de confidentialité. Les organisateurs de réunion peuvent toujours utiliser le chiffrement de bout en bout et appliquer des filigranes si une réunion donnée n’est pas enregistrée.

Pour plus d’informations sur la gestion des options d’enregistrement de réunion, consultez [Gérer les options d’enregistrement de réunion Microsoft Teams pour les réunions sensibles](manage-meeting-recording-options.md).

Pour plus d’informations sur l’enregistrement basé sur des stratégies des réunions à des fins de conformité, consultez [Présentation de l’enregistrement basé sur des stratégies Teams pour les appels & réunions](teams-recording-policy.md).

## <a name="meeting-with-guests-and-external-participants"></a>Réunion avec des invités et des participants externes

Il existe trois types de participants externes qui peuvent participer à des réunions :

- Participants de domaines approuvés
- Invités
- Participants anonymes

Les participants de domaines approuvés rejoignent des réunions via la fonctionnalité [d’accès externe](manage-external-access.md) . Vous pouvez contrôler les domaines, le cas échéant, que votre organisation souhaite approuver. (Ce paramètre affecte également les conversations 1:1 et de groupe avec des personnes dans ces domaines.)

Si [l’accès invité Teams](guest-access.md) est activé pour votre organisation, les invités pourront participer aux réunions. Les paramètres d’accès invité peuvent également être utilisés pour contrôler le mode de partage d’écran des invités, y compris la désactivation du partage d’écran. (L’accès invité est également utilisé pour inviter des invités à des équipes.)

Si le paramètre d’administrateur Teams des **utilisateurs anonymes pouvant rejoindre une réunion** est activé, les participants anonymes pourront participer à des réunions.

Bien que vous puissiez désactiver complètement la jointure anonyme sans affecter les fonctionnalités autres que les réunions, l’accès invité et les domaines approuvés sont utilisés dans des scénarios en dehors des réunions. Si vous souhaitez restreindre l’accès aux réunions à ces participants, mais que vous devez laisser les fonctionnalités activées pour d’autres raisons, vous devez utiliser la salle d’attente.

## <a name="lobby-options"></a>Options de salle d’attente

La salle d’attente de la réunion permet aux organisateurs de la réunion de vérifier les participants avant de les autoriser à entrer dans la réunion. Selon le type de réunion et vos exigences de conformité, vous pouvez autoriser tous les participants à contourner la salle d’attente et à participer directement à la réunion, ou à tenir certains types de participants dans la salle d’attente jusqu’à ce qu’ils soient admis par un organisateur de la réunion. Si vous souhaitez empêcher certains types de personnes , comme les invités, d’assister à des réunions, vous pouvez les faire passer par la salle d’attente, puis l’organisateur de la réunion peut leur refuser l’admission.

Pour le niveau de base, nous autorisons tout le monde, sauf les participants anonymes, à contourner la salle d’attente. Pour les réunions sensibles, nous autorisons uniquement les personnes ayant une invitation à la réunion à contourner la salle d’attente. Pour les réunions très sensibles, nous demandons aux organisateurs d’admettre chaque participant.

En tant qu’administrateur, vous pouvez contrôler la salle d’attente des manières suivantes :

- La **stratégie de réunion d’administration Admission automatique des personnes** (par utilisateur ou groupe)
- Les **utilisateurs rendez-vous peuvent contourner la stratégie de réunion de l’administrateur de la salle d’attente** (par utilisateur ou groupe)
- Le **paramètre Qui peut contourner le paramètre de salle d’attente** dans les étiquettes de confidentialité et les modèles de réunion (par réunion)
- La **Personnes la numérotation peut contourner la** stratégie de réunion de l’administrateur de la salle d’attente (par utilisateur ou groupe) ou dans les étiquettes de confidentialité et les modèles de réunion (par réunion)

Ces paramètres sont également disponibles pour l’organisateur de la réunion, sauf s’ils ont été verrouillés par une étiquette de confidentialité ou un modèle.


Bien que la stratégie d’administration définisse une valeur par défaut, vous avez besoin d’un modèle ou d’une étiquette pour l’appliquer


Si vous êtes dans un secteur hautement réglementé et que vous devez admettre manuellement chaque participant à toutes les réunions de votre organisation, vous pouvez configurer la salle d’attente à l’aide de stratégies de réunion d’administration dans le Centre d’administration Teams. Si votre organisation a différents types de réunions qui ont des exigences différentes en matière de salle d’attente, nous vous recommandons d’utiliser des modèles de réunion ou des étiquettes de confidentialité pour configurer ces paramètres.

Pour plus d’informations, consultez [Configurer la salle d’attente de réunion Microsoft Teams pour les réunions sensibles](configure-lobby-sensitive-meetings.md).

## <a name="related-topics"></a>Rubriques connexes

[Illustrations du cloud Microsoft pour les architectes d’entreprise](/microsoft-365/solutions/cloud-architecture-models)

[Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings)
