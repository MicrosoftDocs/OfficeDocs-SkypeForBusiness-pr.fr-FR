---
title: Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles
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
description: Découvrez comment utiliser des stratégies d’administration Teams avec des étiquettes de confidentialité et des modèles de réunion pour améliorer la sécurité et la conformité pour les réunions sensibles.
ms.openlocfilehash: f0363a7e27df39da7270d9f492048b639f8a3d30
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800080"
---
# <a name="use-teams-meeting-templates-sensitivity-labels-and-admin-policies-together-for-sensitive-meetings"></a>Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Dans les réunions Teams, les organisateurs de réunion peuvent configurer [divers paramètres](https://support.microsoft.com/office/53261366-dbd5-45f9-aae9-a70e6354f88e) qui déterminent les fonctionnalités disponibles dans la réunion. En tant qu’administrateur, vous pouvez désactiver ou appliquer des valeurs spécifiques pour ces paramètres à l’aide d’une combinaison de stratégies d’administration, d’étiquettes de confidentialité et de modèles de réunion.

[Les modèles de réunion](custom-meeting-templates-overview.md) sont créés et gérés dans le Centre d’administration Teams. Les étiquettes de confidentialité sont créées et gérées dans le portail de conformité Microsoft Purview. 

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

En utilisant ensemble des stratégies d’administration, des modèles et des étiquettes, vous pouvez rendre possible divers scénarios de réunion pour répondre aux besoins de conformité et d’entreprise des différents services de votre organisation.

## <a name="policies-labels-templates-and-meetings-settings"></a>Paramètres des stratégies, des étiquettes, des modèles et des réunions

Le tableau suivant présente la liste des fonctionnalités Teams qui peuvent être utiles pour gérer les réunions avec différents besoins de conformité dans votre organisation et où elles peuvent être configurées.

|Fonctionnalité|Stratégie d’administration Teams|Étiquette de confidentialité|Modèle de réunion|Organisateur de la réunion|
|:----|:----|:----|:----|:----|
|Autoriser la caméra pour les participants|Les paramètres de stratégie d’administration vidéo sur IP et Mode pour IP déterminent les participants qui peuvent utiliser leurs caméras.|Aucun paramètre|Peut empêcher ou autoriser l’appareil photo pour les participants. Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|Peut empêcher ou autoriser l’appareil photo pour les participants s’il n’est pas verrouillé par un modèle.|
|Autoriser le micro pour les participants|Le paramètre Mode pour l’audio IP détermine quels participants peuvent utiliser leurs micros.|Aucun paramètre|Peut empêcher ou autoriser le micro pour les participants. Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|Peut empêcher ou autoriser le micro pour les participants s’il n’est pas verrouillé par un modèle.|
|Appliquer un filigrane au flux vidéo de tout le monde|Peut être défini sur Activé ou Désactivé. Si la valeur est Désactivée, elle n’est pas disponible dans les étiquettes de confidentialité, les modèles de réunion ou les paramètres de réunion.|Peut appliquer ou empêcher des filigranes sur les flux vidéo des participants, ou laisser le paramètre non contrôlé.|Peut appliquer ou empêcher des filigranes sur les flux vidéo des participants, sauf si le paramètre est contrôlé par une étiquette de confidentialité.|L’organisateur de la réunion peut activer ou désactiver, sauf si le paramètre est désactivé par la stratégie de l’administrateur ou appliqué par un modèle de réunion ou une étiquette de confidentialité.|
|Appliquer un filigrane au contenu partagé|Peut être défini sur Activé ou Désactivé. Si la valeur est Désactivée, elle n’est pas disponible dans les étiquettes de confidentialité, les modèles de réunion ou les paramètres de réunion.|Peut appliquer ou empêcher des filigranes sur le contenu partagé à l’écran ou laisser le paramètre non contrôlé.|Peut appliquer ou empêcher des filigranes sur le contenu partagé à l’écran, sauf si le paramètre est contrôlé par une étiquette de confidentialité.|L’organisateur de la réunion peut activer ou désactiver, sauf si le paramètre est désactivé par la stratégie de l’administrateur ou appliqué par un modèle de réunion ou une étiquette de confidentialité.|
|Chiffrement de bout en bout|Lorsqu’il est activé, le chiffrement de bout en bout peut être activé par une étiquette de confidentialité, un modèle de réunion ou l’organisateur de la réunion.|Peut appliquer ou empêcher le chiffrement de bout en bout ou laisser le paramètre non contrôlé.|Peut appliquer ou empêcher le chiffrement de bout en bout, sauf si le paramètre est contrôlé par une étiquette de confidentialité.|L’organisateur de la réunion peut activer ou désactiver, sauf si le paramètre est désactivé par la stratégie de l’administrateur ou appliqué par un modèle de réunion ou une étiquette de confidentialité.|
|Gérer ce que voient les participants|Aucun paramètre|Aucun paramètre|Peut être défini sur Activé ou Désactivé et peut appliquer le paramètre ou autoriser l’organisateur de la réunion à le modifier.|L’organisateur de la réunion peut activer ou désactiver, sauf si le paramètre est activé ou désactivé par un modèle de réunion.|
|Conversation de réunion|Peut être défini sur Activé, Désactivé ou Activé pour tout le monde, à l’exception des participants anonymes. S’il est défini sur Désactivé, le paramètre de conversation est désactivé dans les étiquettes, les modèles et les paramètres de réunion.|Peut faire en sorte que la conversation soit activée, désactivée ou réunion uniquement, ou laisser le paramètre non contrôlé.|S’il est activé dans la stratégie d’administration et non contrôlé par une étiquette de confidentialité, peut être défini sur Activé, Désactivé ou réunion uniquement. Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|S’il est activé par la stratégie d’administration et non appliqué par une étiquette ou un modèle de confidentialité, le propriétaire de la réunion peut définir sur Activé, Désactivé ou réunion uniquement.|
|Personnes la numérotation peut contourner la salle d’attente|Définit le paramètre par défaut pour les nouvelles réunions.|Si l’étiquette contrôle les personnes autorisées à contourner la salle d’attente, ce paramètre est appliqué activé ou désactivé, sinon il n’est pas contrôlé.|S’il n’est pas contrôlé par une étiquette de confidentialité, peut être défini sur Activé ou Désactivé. Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|S’il n’est pas appliqué par une étiquette ou un modèle de confidentialité, le propriétaire de la réunion peut définir sur Activé ou Désactivé.|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|Aucun paramètre|Peut empêcher la conversation de réunion d’être copiée. (Ne s’applique pas aux participants anonymes.)|Aucun paramètre|Aucun paramètre|
|Enregistrer automatiquement|Aucun paramètre|Peut appliquer ou empêcher l’enregistrement automatique des réunions ou être laissé non contrôlé.|S’il n’est pas contrôlé par une étiquette de confidentialité, peut être défini sur Activé ou Désactivé et peut appliquer le paramètre ou autoriser l’organisateur de la réunion à le modifier.|L’organisateur de la réunion peut activer ou désactiver le paramètre, sauf si le paramètre est activé ou désactivé par un modèle de réunion ou une étiquette de confidentialité.|
|Qui peut contourner la salle d’attente|Définit le paramètre par défaut pour les nouvelles réunions.|Peut appliquer une option particulière pour qui peut contourner la salle d’attente, ou peut être laissé non contrôlé.|S’il n’est pas contrôlé par une étiquette de confidentialité, sélectionne un paramètre pour qui peut contourner la salle d’attente. Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|L’organisateur de la réunion peut choisir qui peut contourner la salle d’attente, sauf si le paramètre est appliqué par une étiquette ou un modèle.|
|Qui peut présenter|Définit le paramètre par défaut pour les nouvelles réunions. Les valeurs disponibles sont Organisateurs, Tout le monde dans l’organisation et Tout le monde.|Peut appliquer les paramètres de tout le monde, des participants authentifiés, des organisateurs ou des personnes spécifiques, ou peut être laissé non contrôlé.|Aucun paramètre|L’organisateur de la réunion peut sélectionner les personnes autorisées à présenter, sauf si une étiquette de confidentialité est appliquée.|
|Qui peut enregistrer|Aucun paramètre|Peut appliquer les paramètres des organisateurs ou des organisateurs et des présentateurs, ou peut être laissé non contrôlé.|S’il n’est pas contrôlé par une étiquette de confidentialité, sélectionne un paramètre d’organisateurs ou d’organisateurs et de présentateurs.  Le paramètre peut être appliqué ou l’organisateur de la réunion peut être autorisé à changer.|L’organisateur de la réunion peut choisir les personnes autorisées à enregistrer ( organisateurs ou organisateurs et présentateurs), sauf si le paramètre est appliqué par une étiquette ou un modèle.|

## <a name="admin-policies-effect-on-sensitivity-labels-and-meeting-templates"></a>Administration l’effet des stratégies sur les étiquettes de confidentialité et les modèles de réunion

Bien que certaines stratégies d’administration (telles que les paramètres de salle d’attente et les personnes qui peuvent présenter) spécifient les valeurs par défaut que l’organisateur de la réunion peut modifier, la plupart des stratégies d’administration déterminent si une fonctionnalité donnée est disponible pour les utilisateurs.

Si une fonctionnalité n’est pas disponible pour un utilisateur donné parce que la stratégie d’administration l’a désactivée pour lui, cette fonctionnalité ne peut pas être appliquée par une étiquette de confidentialité ou un modèle de réunion.

Par exemple, si vous créez une étiquette *hautement sensible* et que vous la configurez pour appliquer le filigrane et le chiffrement de bout en bout, cette application n’aura lieu que si le filigrane et le chiffrement de bout en bout sont activés pour l’organisateur de la réunion dans la stratégie d’administration.

Lorsque vous planifiez vos modèles de réunion et étiquettes de confidentialité, assurez-vous que les paramètres que vous souhaitez contrôler avec eux sont activés dans les stratégies d’administration si nécessaire.

## <a name="sensitivity-labels-and-templates-together"></a>Étiquettes de confidentialité et modèles ensemble

Certains paramètres sont uniquement disponibles dans les étiquettes de confidentialité et d’autres uniquement dans les modèles. Plusieurs sont disponibles dans les deux :

- Conversation
- Chiffrement de bout en bout
- Paramètres de la salle d’attente
- Enregistrement de réunion
- Tatouage

Chaque fois qu’une étiquette de confidentialité est utilisée, les paramètres configurés dans l’étiquette sont prioritaires sur les paramètres de modèle ou d’organisateur de réunion.

Les paramètres d’une étiquette de confidentialité peuvent être laissés non contrôlés lors de la création de l’étiquette, ce qui permet à un modèle ou à l’organisateur de la réunion de contrôler ces paramètres.

Les étiquettes de confidentialité sont souvent utilisées à plusieurs fins : l’étiquetage des documents, des sites et des e-mails, ainsi que des réunions. Vous pouvez éviter de créer des étiquettes supplémentaires uniquement pour les réunions en utilisant des modèles avec les étiquettes pour prendre en compte les variations au sein d’un type particulier de réunion.

Par exemple, votre service marketing peut avoir des exigences différentes pour les réunions sensibles que le service de recherche. Vous pouvez configurer les paramètres communs aux deux dans une étiquette de confidentialité, puis mettre des modèles distincts à la disposition des deux groupes qui affinent les paramètres de réunion pour ce groupe. Les deux modèles peuvent utiliser la même étiquette.

## <a name="user-based-policies-and-meeting-based-policies"></a>Stratégies basées sur l’utilisateur et stratégies basées sur les réunions

Les stratégies Teams, y compris les stratégies de réunion, s’appliquent au niveau de l’utilisateur ou du groupe. Les paramètres d’étiquette de confidentialité et de modèle s’appliquent au niveau de la réunion individuelle où ces étiquettes et modèles sont utilisés. Déterminez où il est judicieux de configurer les paramètres dans les stratégies d’administration Teams par rapport aux étiquettes ou modèles de confidentialité.

Voici quelques exemples :

Si vous souhaitez des paramètres de lobby par défaut différents pour le service de recherche et le service marketing, vous pouvez configurer ces paramètres par défaut à l’aide de stratégies d’administration et les modifier à l’aide d’étiquettes ou de modèles.

Si vous souhaitez que les filigranes soient disponibles uniquement pour les responsables de la gouvernance, vous pouvez les activer uniquement pour les personnes qui utilisent une stratégie d’administration. Vous pouvez ensuite avoir des étiquettes ou des modèles qui appliquent le filigrane, mais le filigrane sera utilisé uniquement dans les réunions organisées par les responsables de la gouvernance.

## <a name="different-meeting-types-with-the-same-sensitivity"></a>Différents types de réunion avec la même sensibilité

L’utilisation de modèles et d’étiquettes ensemble peut être utile si vous avez différents types de réunions qui ont la même sensibilité. Par exemple, si certaines de vos réunions sensibles sont interactives et que d’autres sont des présentations où l’interaction des participants est minimale, vous pouvez créer deux modèles :
- Un qui désactive la vidéo et l’audio des participants à utiliser pour les présentations
- Un qui laisse la vidéo et l’audio à la discrétion de l’organisateur de la réunion à utiliser pour les réunions interactives

Les deux modèles peuvent utiliser l’étiquette *Sensible* qui contrôlerait des paramètres supplémentaires, tels que qui peut contourner la salle d’attente et qui peut présenter.

## <a name="specify-default-values-that-meeting-organizers-can-change"></a>Spécifier les valeurs par défaut que les organisateurs de réunion peuvent modifier

Bien que les étiquettes appliquent généralement un paramètre particulier, les modèles peuvent soit appliquer un paramètre, soit autoriser l’organisateur de la réunion à le modifier. Cela vous permet d’implémenter des paramètres par défaut qui répondent à vos besoins de conformité tout en donnant aux organisateurs de la réunion la possibilité de remplacer le paramètre si nécessaire.

Par exemple, pour un niveau de protection de base, vous pouvez utiliser une étiquette de confidentialité pour désactiver le filigrane. En même temps, vous pouvez utiliser un modèle pour définir la valeur par défaut pour qui peut contourner la salle d’attente, mais autoriser l’organisateur de la réunion à modifier le paramètre si nécessaire.

Vous pouvez affecter votre étiquette de protection de base au modèle afin que les deux soient utilisées lorsqu’un organisateur de réunion choisit ce modèle.

Certaines stratégies d’administration peuvent également être utilisées pour définir une valeur par défaut qui peut être modifiée par un organisateur de réunion. Il s’agit notamment des contrôles de salle d’attente et des personnes autorisées à présenter.

## <a name="related-topics"></a>Rubriques connexes

[Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md)

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings)
