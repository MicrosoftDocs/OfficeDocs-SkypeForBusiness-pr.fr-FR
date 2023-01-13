---
title: Configurer des réunions Teams avec protection pour les données hautement sensibles
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
description: Découvrez comment configurer des réunions Teams pour la protection des informations hautement sensibles à l’aide de modèles et d’étiquettes de confidentialité.
ms.openlocfilehash: 0d49cc4305f77b4b4208cc0f7418d5506155d0d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800261"
---
# <a name="configure-teams-meetings-with-protection-for-highly-sensitive-data"></a>Configurer des réunions Teams avec protection pour les données hautement sensibles

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Pour le niveau de protection *hautement sensible* , nous allons examiner deux scénarios différents :
- Réunions hautement sensibles où les participants participent et interagissent avec les présentateurs
- Présentations très sensibles où les participants n’interagissent pas et consultent simplement la présentation

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

#### <a name="highly-sensitive-meetings"></a>Réunions très sensibles

Pour les réunions très sensibles, nous allons restreindre qui peut contourner la salle d’attente, qui peut présenter, quand les participants peuvent discuter, et nous bloquerons la copie à partir de la conversation de réunion. Nous allons également activer le chiffrement et le filigrane de bout en bout pour la vidéo et le contenu partagés. Étant donné que nous utilisons des filigranes, l’enregistrement des réunions est désactivé.

Le tableau suivant décrit les actions que nous allons restreindre pour les réunions très sensibles et l’emplacement où ces paramètres sont configurés.

|Fonctionnalité|Paramètres|Lieu|Appliquées|
|:------|:------|:-------|:-------|
|Autoriser la caméra pour les participants|**Activé**|Modèle|Non|
|Autoriser le micro pour les participants|**Activé**|Modèle|Non|
|Appliquer un filigrane au flux vidéo de tout le monde|**Activé**|Étiquette|Oui|
|Appliquer un filigrane au contenu partagé|**Activé**|Étiquette|Oui|
|Chiffrement de bout en bout|**Activé**|Étiquette|Oui|
|Gérer ce que voient les participants|**Activé**|Modèle|Oui|
|Conversation de réunion|**Uniquement en réunion**|Modèle|Oui|
|Personnes la numérotation peut contourner la salle d’attente|**Désactivé**|Étiquette|Oui|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|**Activé**|Étiquette|Oui|
|Enregistrer automatiquement|(Désactivé en raison du filigrane et du chiffrement)|N/A|N/A|
|Qui peut contourner la salle d’attente|**Seuls les organisateurs et les co-organisateurs**|Étiquette|Oui|
|Qui peut présenter|**Seuls les organisateurs et les co-organisateurs**|Étiquette|Oui|
|Qui peut enregistrer|(Désactivé en raison du filigrane et du chiffrement)|N/A|N/A|

Les paramètres répertoriés comme étant appliqués sont appliqués par l’étiquette de confidentialité ou le modèle de réunion. Les paramètres qui ne sont pas appliqués peuvent être modifiés par l’organisateur de la réunion.

#### <a name="highly-sensitive-presentations"></a>Présentations très sensibles

Pour les présentations très sensibles , où nous ne prévoyons pas d’interaction avec les participants à la réunion, nous allons désactiver les micros et les caméras des participants, et désactiver la conversation de réunion.

Si vous souhaitez autoriser les participants à poser des questions au présentateur, les organisateurs de la réunion peuvent activer la fonctionnalité Q&R. (Assurez-vous qu’il est activé dans les stratégies de réunion d’administration Teams.)

Le tableau suivant décrit les actions que nous allons restreindre pour les présentations très sensibles et l’emplacement où ces paramètres sont configurés.

|Fonctionnalité|Paramètres|Lieu|Appliquées|
|:------|:------|:-------|:-------|
|Autoriser la caméra pour les participants|**Désactivé**|Modèle|Oui|
|Autoriser le micro pour les participants|**Désactivé**|Modèle|Oui|
|Appliquer un filigrane au flux vidéo de tout le monde|**Activé**|Étiquette|Oui|
|Appliquer un filigrane au contenu partagé|**Activé**|Étiquette|Oui|
|Chiffrement de bout en bout|**Activé**|Étiquette|Oui|
|Gérer ce que voient les participants|**Activé**|Modèle|Oui|
|Conversation de réunion|**Désactivé**|Modèle|Oui|
|Personnes la numérotation peut contourner la salle d’attente|**Désactivé**|Étiquette|Oui|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|**Activé**|Étiquette|Oui|
|Enregistrer automatiquement|(Désactivé en raison du filigrane et du chiffrement)|N/A|N/A|
|Qui peut contourner la salle d’attente|**Seuls les organisateurs et les co-organisateurs**|Étiquette|Oui|
|Qui peut présenter|**Seuls les organisateurs et les co-organisateurs**|Étiquette|Oui|
|Qui peut enregistrer|(Désactivé en raison du filigrane et du chiffrement)|N/A|N/A|

Les paramètres répertoriés comme étant appliqués sont appliqués par l’étiquette de confidentialité ou le modèle de réunion. Les paramètres qui ne sont pas appliqués peuvent être modifiés par l’organisateur de la réunion.

## <a name="options-for-recording-meetings"></a>Options d’enregistrement des réunions

Pour le niveau de protection *hautement sensible* , nous utilisons le filigrane et le chiffrement de bout en bout pour les réunions et les présentations. Toutefois, l’utilisation de ces fonctionnalités empêche l’enregistrement de la réunion. Si vous avez besoin d’enregistrer des réunions très sensibles, nous vous recommandons de ne pas configurer les filigranes et le chiffrement de bout en bout dans le cadre de l’étiquette de confidentialité. Ils peuvent toujours être utilisés par les organisateurs de réunion pour les réunions qu’ils n’ont pas besoin d’enregistrer.

## <a name="presentation-options-for-highly-sensitive-meetings"></a>Options de présentation pour les réunions hautement sensibles

Pour les réunions *très sensibles* , nous mettons en œuvre des paramètres spécifiques pour les personnes autorisées à présenter, ainsi que la façon dont le contenu est partagé.

En activant **Gérer ce que les participants peuvent voir**, nous nous assurons que les organisateurs de la réunion peuvent vérifier le contenu partagé avant qu’il ne soit affiché à l’écran pour les participants. Dans cet exemple, nous utilisons un modèle pour l’activer par défaut, mais vous pouvez également l’appliquer dans le modèle si nécessaire.

En définissant **Qui peut présenter** sur **Uniquement les organisateurs et co-organisateurs** dans l’étiquette de confidentialité, nous nous assurons que les seules personnes qui peuvent présenter sont celles que l’organisateur de la réunion a l’intention de présenter.

## <a name="lobby-options-for-sensitive-meetings"></a>Options de salle d’attente pour les réunions sensibles

Nous allons utiliser l’étiquette de confidentialité pour empêcher toute personne autre que les organisateurs de réunion de contourner la salle d’attente. Cela permet aux organisateurs de vérifier chaque participant et de s’assurer qu’ils doivent être admis.

## <a name="participation-options-for-highly-sensitive-meetings"></a>Options de participation pour les réunions très sensibles

Bien que la conversation puisse être contrôlée avec l’étiquette de confidentialité, nous allons utiliser des modèles dans ce cas afin que les modèles de réunion et de présentation puissent partager la même étiquette. Nous allons limiter la conversation aux réunions uniquement pour les réunions et la désactiver complètement pour les présentations. (Les organisateurs peuvent utiliser la fonctionnalité Q&A dans les présentations pour autoriser les commentaires ou les questions du public.)

Pour les réunions et les présentations, nous allons également empêcher la copie du contenu de conversation dans le Presse-papiers.

Bien que nous laissons le micro et la caméra des participants activés pour les réunions, nous les désactivons pour les présentations.

## <a name="sensitivity-labels"></a>Étiquettes de confidentialité

Pour le niveau de protection sensible, nous allons utiliser une étiquette de confidentialité que vous pouvez utiliser directement dans une réunion ou dans le cadre d’un modèle de réunion. Selon la configuration que vous choisissez, cette étiquette peut également être utilisée pour classifier des équipes et des fichiers individuels.

Si vous avez déjà déployé des étiquettes de confidentialité dans votre organisation, réfléchissez à la façon dont cette étiquette s’adapte à votre stratégie d’étiquette globale. Vous pouvez modifier le nom ou les paramètres si nécessaire pour répondre aux besoins de votre organisation. Si vous avez déjà une étiquette que vous utilisez pour les informations sensibles, vous pouvez modifier l’étiquette et y ajouter des réunions Teams.

> [!IMPORTANT]
> Si une étiquette de confidentialité qui restreint la copie à partir de la conversation est spécifiée en tant qu’étiquette de canal par défaut dans une étiquette de conteneur, les équipes avec cette étiquette de conteneur limitent la copie à partir de la conversation pour tous les canaux de l’équipe, à la fois dans et hors des réunions de canal.

Pour créer une étiquette de confidentialité
1. Ouvrez le [portail de conformité Microsoft Purview](https://compliance.microsoft.com).
1. Sous **Solutions**, cliquez sur **Protection des informations**.
1. Cliquez sur **Créer une étiquette**.
1. Donnez un nom à l’étiquette. Nous vous suggérons **Hautement sensible**, mais vous pouvez choisir un autre nom si celui-ci est déjà utilisé.
1. Ajoutez un nom complet et une description, puis cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette** , sélectionnez **Éléments** et **Inclure les réunions**. (Notez que vous pouvez sélectionner d’autres options si vous souhaitez utiliser cette étiquette à d’autres fins.)
1. Sélectionnez **Suivant**.
1. Continuez à sélectionner les options que vous souhaitez utiliser avec cette étiquette, puis dans la page **Paramètres des réunions et des conversations Teams** , choisissez les valeurs suivantes :
    1. Sélectionnez **Contrôler qui peut contourner la salle d’attente** , puis sélectionnez **Uniquement organisateurs et co-organisateurs** dans la liste déroulante.
    1. Vérifier que **l’option Autoriser les utilisateurs de connexion à contourner la salle d’attente** est décochée
    1. Sélectionnez **Contrôler qui peut présenter** et sélectionnez **Uniquement les organisateurs et les co-organisateurs** dans la liste déroulante.
    1. Sélectionnez **Contrôler le chiffrement de bout en bout pour la vidéo et l’audio de réunion** , puis **définissez Appliquer le chiffrement de bout en bout** sur **Activé**.
    1. Sélectionnez **Contrôler les filigranes** , puis **définissez Appliquer le filigrane au contenu partagé** et **Appliquer le filigrane au flux vidéo de tout le monde** sur **Activé**.
    1. Sélectionnez **Empêcher la copie du contenu de conversation dans le Presse-papiers**.
    1. Configurez tous les autres paramètres dont vous avez besoin pour votre organisation.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-highly-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-highly-sensitive-large.png":::-->
1. Sélectionnez **Suivant**.
1. Complétez l’Assistant avec les paramètres supplémentaires que vous souhaitez utiliser, puis sélectionnez **Créer une étiquette**, puis sélectionnez **Terminé**.

Une fois que vous avez créé l’étiquette, vous devez la publier pour les utilisateurs qui l’utiliseront. Pour une protection hautement sensible, nous allons mettre l’étiquette à la disposition de tous les utilisateurs. Vous publiez l’étiquette dans le portail de conformité Microsoft Purview, sous l’onglet **Stratégies d’étiquette** de la page **Information protection**. Si vous avez une stratégie existante qui s’applique à tous les utilisateurs, ajoutez cette étiquette à cette stratégie. Si vous devez créer une stratégie, consultez [Publier des étiquettes de confidentialité en créant une stratégie d’étiquette](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Pour plus d’informations sur l’utilisation des étiquettes de confidentialité avec les réunions, consultez [Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modèles de réunion

Dans le niveau de protection *hautement sensible* , nous configurons les paramètres suivants à l’aide d’un modèle de réunion :

- **Autoriser la caméra pour les** -  participants **Activé**, mais non appliqué pour les réunions et **désactivé** pour les présentations.
- **Autoriser le micro pour les** -  participants **Activé**, mais non appliqué pour les réunions et **désactivé** pour les présentations.
- **Gérer ce que les participants peuvent voir** - Appliqué **pour** les réunions et les présentations.
- **Conversation de réunion** : appliquée à **en réunion uniquement** pour les réunions et appliquée à **Désactivé** pour les présentations.

Étant donné que ces paramètres diffèrent entre les réunions et les présentations, nous allons créer un modèle pour chacune d’elles partageant la même étiquette de confidentialité.

#### <a name="highly-sensitive-meetings-template"></a>Modèle de réunions hautement sensibles

Pour créer un modèle de réunion pour les réunions hautement sensibles

1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Modèles de réunion**.
1. Sélectionnez **Ajouter.**
1. Tapez un nom et une description pour le modèle.
1. Dans la section **Appliquer une étiquette de confidentialité** , choisissez l’étiquette que vous avez créée ci-dessus.
1. Sélectionnez **Appliquer l’étiquette de confidentialité**, puis **verrouiller**.
1. Définissez **Conversation de réunion** **sur En réunion uniquement** , puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. Définissez **Gérer ce que les participants voient** **sur Activé** , puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. Modifiez les paramètres supplémentaires si vous le souhaitez.
1. Pour empêcher l’organisateur de la réunion de modifier un paramètre, sélectionnez-le, puis **sélectionnez Verrouiller**.
1. Pour empêcher l’organisateur de la réunion de voir un paramètre, sélectionnez-le, puis **sélectionnez Masquer**.
1. Sélectionnez **Enregistrer**.

#### <a name="highly-sensitive-presentations-template"></a>Modèle de présentations hautement sensibles

Pour créer un modèle de réunion pour les présentations très sensibles

1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Modèles de réunion**.
1. Sélectionnez **Ajouter.**
1. Tapez un nom et une description pour le modèle.
1. Dans la section **Appliquer une étiquette de confidentialité** , choisissez l’étiquette que vous avez créée ci-dessus.
1. Sélectionnez **Appliquer l’étiquette de confidentialité**, puis **verrouiller**.
1. **Définissez Autoriser le micro pour les participants** sur **Activé**, puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. **Définissez Autoriser la caméra pour les participants** sur **Activé**, puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. Définissez **Conversation de réunion** sur **Désactivé** , puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. Définissez **Gérer ce que les participants voient** **sur Activé** , puis sélectionnez le paramètre et **sélectionnez Verrouiller**.
1. Modifiez les paramètres supplémentaires si vous le souhaitez.
1. Pour empêcher l’organisateur de la réunion de modifier un paramètre, sélectionnez-le, puis **sélectionnez Verrouiller**.
1. Pour empêcher l’organisateur de la réunion de voir un paramètre, sélectionnez-le, puis **sélectionnez Masquer**.
1. Sélectionnez **Enregistrer**.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles](meeting-templates-sensitivity-labels-policies.md)

[Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings)
