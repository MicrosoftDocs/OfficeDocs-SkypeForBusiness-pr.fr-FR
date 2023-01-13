---
title: Configurer des réunions Teams avec protection pour les données sensibles
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
description: Découvrez comment configurer des réunions Teams pour la protection des informations sensibles à l’aide de modèles et d’étiquettes de confidentialité.
ms.openlocfilehash: 3aae927f29464f3e5d8a9e695c170ded06d3dd1f
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800095"
---
# <a name="configure-teams-meetings-with-protection-for-sensitive-data"></a>Configurer des réunions Teams avec protection pour les données sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Pour le niveau *de protection sensible* , nous allons restreindre qui peut contourner la salle d’attente, qui peut présenter et qui peut enregistrer. Vous pouvez également restreindre des actions supplémentaires si votre organisation en a besoin.

Le tableau suivant décrit les actions que nous allons restreindre pour les réunions sensibles et l’emplacement où ces paramètres sont configurés.

|Fonctionnalité|Paramètres|Lieu|Appliquées|
|:------|:------|:-------|:-------|
|Autoriser la caméra pour les participants|**Activé**|Modèle|Non|
|Autoriser le micro pour les participants|**Activé**|Modèle|Non|
|Appliquer un filigrane au flux vidéo de tout le monde|**Désactivé**|Modèle|Non|
|Appliquer un filigrane au contenu partagé|**Désactivé**|Modèle|Non|
|Chiffrement de bout en bout|**Désactivé**|Modèle|Non|
|Gérer ce que voient les participants|**Activé**|Modèle|Non|
|Conversation de réunion|**Activé**|Modèle|Non|
|Personnes la numérotation peut contourner la salle d’attente|**Désactivé**|Modèle|Oui|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|**Désactivé**|Étiquette|Non|
|Enregistrer automatiquement|**Désactivé**|Modèle|Non|
|Qui peut contourner la salle d’attente|**Seules les personnes qui ont été invitées**|Étiquette|Oui|
|Qui peut présenter|**Membres de mon organisation et invités**|Étiquette|Oui|
|Qui peut enregistrer|**Organisateur et co-organisateurs**|Étiquette|Oui|

Les paramètres répertoriés comme étant appliqués sont appliqués par l’étiquette de confidentialité ou le modèle de réunion. Les paramètres qui ne sont pas appliqués peuvent être modifiés par l’organisateur de la réunion.

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

## <a name="presentation-options-for-sensitive-meetings"></a>Options de présentation pour les réunions sensibles

Pour le niveau *de protection sensible* , nous mettons en œuvre des paramètres spécifiques pour les personnes autorisées à présenter, ainsi que la façon dont le contenu est partagé.

En activant **Gérer ce que les participants peuvent voir**, nous nous assurons que les organisateurs de la réunion peuvent vérifier le contenu partagé avant qu’il ne soit affiché à l’écran pour les participants. Dans cet exemple, nous utilisons un modèle pour l’activer par défaut, mais vous pouvez également l’appliquer dans le modèle si nécessaire.

En définissant **Qui peut présenter** sur **Personnes dans mon organisation et les invités** dans l’étiquette de confidentialité, nous supprimons la possibilité de présenter des participants anonymes dans la réunion. Vous pouvez limiter cela aux **organisateurs et co-organisateurs uniquement** si nécessaire. (Nous allons le faire pour le niveau de protection *hautement sensible* .)

Nous limiterons également l’enregistrement à l’organisateur et aux co-organisateurs à l’aide de l’étiquette de confidentialité.

## <a name="lobby-options-for-sensitive-meetings"></a>Options de salle d’attente pour les réunions sensibles

Nous utiliserons l’étiquette de confidentialité pour empêcher toute personne autre que les participants invités (personnes directement invitées par l’organisateur ou auxquelles une invitation a été transmise) de contourner la salle d’attente. Cela donne un niveau de protection supplémentaire en permettant à l’organisateur de vérifier quiconque n’a pas directement envoyé une invitation avant de l’admettre à la réunion. Vous pouvez restreindre davantage ce paramètre en choisissant **Uniquement organisateurs et co-organisateurs**. (Nous allons le faire pour le niveau de protection *hautement sensible* .)


## <a name="sensitivity-labels"></a>Étiquettes de confidentialité

Pour le niveau de protection sensible, nous allons utiliser une étiquette de confidentialité que vous pouvez utiliser directement dans une réunion ou dans le cadre d’un modèle de réunion. Selon la configuration que vous choisissez, cette étiquette peut également être utilisée pour classifier des équipes et des fichiers individuels.

Si vous avez déjà déployé des étiquettes de confidentialité dans votre organisation, réfléchissez à la façon dont cette étiquette s’adapte à votre stratégie d’étiquette globale. Vous pouvez modifier le nom ou les paramètres si nécessaire pour répondre aux besoins de votre organisation. Si vous avez déjà une étiquette que vous utilisez pour les informations sensibles, vous pouvez modifier l’étiquette et y ajouter des réunions Teams.

Pour créer une étiquette de confidentialité
1. Ouvrez le [portail de conformité Microsoft Purview](https://compliance.microsoft.com).
1. Sous **Solutions**, cliquez sur **Protection des informations**.
1. Cliquez sur **Créer une étiquette**.
1. Donnez un nom à l’étiquette. Nous vous suggérons **Sensible**, mais vous pouvez choisir un autre nom si celui-ci est déjà utilisé.
1. Ajoutez un nom complet et une description, puis cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette** , sélectionnez **Éléments** et **Inclure les réunions**. (Notez que vous pouvez sélectionner d’autres options si vous souhaitez utiliser cette étiquette à d’autres fins.)
1. Sélectionnez **Suivant**.
1. Continuez à sélectionner les options que vous souhaitez utiliser avec cette étiquette, puis dans la page **Paramètres des réunions et des conversations Teams** , choisissez les valeurs suivantes :
    1. Sélectionnez **Contrôler qui peut contourner la salle d’attente** et choisissez **Uniquement les personnes qui ont été invitées** dans la liste déroulante.
    1. Sélectionnez **Contrôler qui peut présenter** et choisissez **Personnes dans mon organisation et les invités dans** la liste déroulante.
    1. Sélectionnez **Qui peut enregistrer** et choisissez **Organisateurs et co-organisateurs** dans la liste déroulante.
    1. Configurez tous les autres paramètres dont vous avez besoin pour votre organisation.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-sensitive-large.png":::-->
1. Sélectionnez **Suivant**.
1. Complétez l’Assistant avec les paramètres supplémentaires que vous souhaitez utiliser, puis sélectionnez **Créer une étiquette**, puis sélectionnez **Terminé**.

Une fois que vous avez créé l’étiquette, vous devez la publier pour les utilisateurs qui l’utiliseront. Pour la protection sensible, nous allons mettre l’étiquette à la disposition de tous les utilisateurs. Vous publiez l’étiquette dans le portail de conformité Microsoft Purview, sous l’onglet **Stratégies d’étiquette** de la page **Information protection**. Si vous avez une stratégie existante qui s’applique à tous les utilisateurs, ajoutez cette étiquette à cette stratégie. Si vous devez créer une stratégie, consultez [Publier des étiquettes de confidentialité en créant une stratégie d’étiquette](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Pour plus d’informations sur l’utilisation des étiquettes de confidentialité avec les réunions, consultez [Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modèles de réunion

L’un des avantages de l’utilisation de modèles est que vous pouvez créer plusieurs modèles qui utilisent la même étiquette de confidentialité qui verrouille différents paramètres. Par exemple, si certaines de vos réunions sensibles sont des présentations où l’interaction des participants est minimale, vous pouvez créer un modèle qui désactive la vidéo des participants et même la conversation, et un autre modèle qui laisse ces options à l’organisateur de la réunion. Les deux modèles utilisent l’étiquette *Sensible* .

Dans le niveau *de protection sensible* , nous allons utiliser le modèle pour empêcher les personnes qui composent par téléphone de contourner la salle d’attente. S’il existe certains types de réunions où vous souhaitez autoriser les personnes appelant par téléphone à contourner la salle d’attente, envisagez d’utiliser un modèle distinct avec la même étiquette pour ces réunions.

Pour créer un modèle de réunion personnalisé

1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Modèles de réunion**.
1. Sélectionnez **Ajouter.**
1. Tapez un nom et une description pour le modèle.
1. Dans la section **Appliquer une étiquette de confidentialité** , choisissez l’étiquette que vous avez créée ci-dessus.
1. Sélectionnez **Appliquer l’étiquette de confidentialité**, puis **verrouiller**.
1. Assurez-vous **que Personnes appel sur mon téléphone peut contourner la salle d’attente** est défini sur **Désactivé**, puis sélectionnez-la et sélectionnez **Verrouiller**.
1. Modifiez les paramètres supplémentaires si vous le souhaitez.
1. Pour empêcher l’organisateur de la réunion de modifier un paramètre, sélectionnez-le, puis **sélectionnez Verrouiller**.
1. Pour empêcher l’organisateur de la réunion de voir un paramètre, sélectionnez-le, puis **sélectionnez Masquer**.
1. Sélectionnez **Enregistrer**.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles](meeting-templates-sensitivity-labels-policies.md)
