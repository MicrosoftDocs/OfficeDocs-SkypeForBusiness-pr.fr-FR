---
title: Configurer des réunions Teams avec la protection de base
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
description: Découvrez comment configurer des réunions Teams pour un niveau de protection de base à l’aide de modèles et d’étiquettes de confidentialité.
ms.openlocfilehash: 3770bb03c1986c4a6bbef72408340fd791b058f1
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800102"
---
# <a name="configure-teams-meetings-with-baseline-protection"></a>Configurer des réunions Teams avec la protection de base

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Pour le niveau de protection *de base* , nous allons limiter les personnes autorisées à contourner la salle d’attente à l’aide d’une étiquette de confidentialité et définir une valeur par défaut pour qui peut présenter une stratégie d’administration Teams. Vous pouvez également restreindre des actions supplémentaires si votre organisation en a besoin.

> [!Note]
> Les paramètres de réunion dans les étiquettes de confidentialité et les modèles de réunion personnalisés nécessitent Teams Premium.

Le tableau suivant décrit les actions que nous limiterons pour les réunions de base et l’emplacement où ces paramètres sont configurés.

|Fonctionnalité|Paramètres|Lieu|Appliquées|
|:------|:------|:-------|:-------|
|Autoriser la caméra pour les participants|**Activé**|Modèle|Non|
|Autoriser le micro pour les participants|**Activé**|Modèle|Non|
|Appliquer un filigrane au flux vidéo de tout le monde|**Désactivé**|Étiquette|Oui|
|Appliquer un filigrane au contenu partagé|**Désactivé**|Étiquette|Oui|
|Chiffrement de bout en bout|**Désactivé**|Étiquette|Oui|
|Gérer ce que voient les participants|**Désactivé**|Modèle|Non|
|Conversation de réunion|**Activé**|Modèle|Non|
|Personnes la numérotation peut contourner la salle d’attente|**Désactivé**|Modèle|Oui|
|Empêcher la copie du contenu de conversation dans le Presse-papiers|**Désactivé**|Étiquette|Oui|
|Enregistrer automatiquement|**Désactivé**|Modèle|Non|
|Qui peut contourner la salle d’attente|**Personnes dans mon organisation, les membres d’organisations de confiance et les invités**|Modèle|Non|
|Qui peut présenter|**Tout le monde dans l’organisation, mais l’utilisateur peut remplacer**|Centre d’administration Microsoft Teams|Non|
|Qui peut enregistrer|**Organisateurs et présentateurs**|Modèle|Non|

Les paramètres répertoriés comme étant appliqués sont appliqués par l’étiquette de confidentialité ou le modèle de réunion. Les paramètres qui ne sont pas appliqués peuvent être modifiés par l’organisateur de la réunion.

## <a name="default-values-for-who-can-present"></a>Valeurs par défaut pour **Qui peut présenter**

La valeur par défaut de **Qui peut présenter** est **Tout le monde**. Pour le niveau de protection de base, nous allons définir une valeur par défaut plus sécurisée **de Tous les membres de l’organisation** que les organisateurs de réunion peuvent modifier s’ils le souhaitent.

Nous pouvons définir cette valeur avec une étiquette de confidentialité, mais la valeur sera appliquée pour toutes les réunions avec cette étiquette. Ce paramètre n’est pas disponible dans les modèles de réunion. Nous allons donc le définir dans le Centre d’administration Teams.

Pour configurer les personnes autorisées à participer aux réunions
1. Dans le Centre d’administration Teams, développez **Réunions** et sélectionnez **Stratégies de réunion**.
1. Sélectionnez la stratégie à mettre à jour.
1. Sous **Participants & invités**, définissez **Qui peut présenter dans les réunions sur** **Tout le monde dans l’organisation, mais l’utilisateur peut remplacer**.
1. Sélectionnez **Enregistrer**.

## <a name="watermarks-and-end-to-end-encryption"></a>Filigranes et chiffrement de bout en bout

Dans le niveau de protection *de base* , nous allons désactiver les filigranes et le chiffrement de bout en bout à l’aide d’une étiquette de confidentialité. Cela empêchera les organisateurs de réunion d’utiliser ces fonctionnalités. Les filigranes et le chiffrement de bout en bout sont plus applicables aux réunions sensibles.

Le chiffrement de bout en bout et les filigranes désactivent certaines autres fonctionnalités telles que l’enregistrement des réunions. Les désactiver pour le niveau de protection *de base* peut éviter les instances où les organisateurs de réunion utilisent ces fonctionnalités sans se rendre compte des limites qu’elles imposent.

Si vous travaillez dans un secteur hautement réglementé, vous souhaiterez peut-être conserver ces fonctionnalités disponibles même dans le niveau de protection de *base* .

## <a name="sensitivity-labels"></a>Étiquettes de confidentialité

Pour le niveau de protection *de base* , nous allons utiliser une étiquette de confidentialité que vous pouvez utiliser directement dans une réunion ou dans le cadre d’un modèle de réunion. Selon la configuration que vous choisissez, cette étiquette peut également être utilisée pour classifier des équipes et des fichiers individuels.

Si vous avez déjà déployé des étiquettes de confidentialité dans votre organisation, réfléchissez à la façon dont cette étiquette s’adapte à votre stratégie d’étiquette globale. Vous pouvez modifier le nom ou les paramètres affichés ci-dessous si nécessaire pour répondre aux besoins de votre organisation. Si vous disposez déjà d’une étiquette que vous utilisez pour la protection de base ou générale, vous pouvez modifier l’étiquette et y ajouter des réunions Teams.

Pour créer une étiquette de confidentialité
1. Ouvrez le [portail de conformité Microsoft Purview](https://compliance.microsoft.com).
1. Sous **Solutions**, cliquez sur **Protection des informations**.
1. Cliquez sur **Créer une étiquette**.
1. Donnez un nom à l’étiquette. Nous vous suggérons **Sensible**, mais vous pouvez choisir un autre nom si celui-ci est déjà utilisé.
1. Ajoutez un nom complet et une description, puis cliquez sur **Suivant**.
1. Dans la page **Définir l’étendue de cette étiquette** , sélectionnez **Éléments** et **Inclure les réunions**. (Notez que vous pouvez sélectionner d’autres options si vous souhaitez utiliser cette étiquette à d’autres fins.)
1. Sélectionnez **Suivant**.
1. Continuez à sélectionner les options que vous souhaitez utiliser avec cette étiquette, puis dans la page **Paramètres des réunions et des conversations Teams** , choisissez les valeurs suivantes :
    1. Sélectionnez **Contrôler le chiffrement de bout en bout pour la vidéo et l’audio de réunion** , puis **définissez Appliquer le chiffrement de bout en bout** sur **Désactivé**.
    1. Sélectionnez **Contrôler les filigranes** et **définissez Appliquer les filigranes au contenu partagé** et **Appliquer les filigranes au flux vidéo de tout le monde** sur **Désactivé**.
    1. Configurez tous les autres paramètres dont vous avez besoin pour votre organisation.
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-baseline-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-baseline-large.png":::-->
1. Sélectionnez **Suivant**.
1. Complétez l’Assistant avec les paramètres supplémentaires que vous souhaitez utiliser, puis sélectionnez **Créer une étiquette**, puis sélectionnez **Terminé**.

Une fois que vous avez créé l’étiquette, vous devez la publier pour les utilisateurs qui l’utiliseront. Pour la protection de base, nous allons mettre l’étiquette à la disposition de tous les utilisateurs. Vous publiez l’étiquette dans le portail de conformité Microsoft Purview, sous l’onglet **Stratégies d’étiquette** de la page **Information protection**. Si vous avez une stratégie existante qui s’applique à tous les utilisateurs, ajoutez cette étiquette à cette stratégie. Si vous devez créer une stratégie, consultez [Publier des étiquettes de confidentialité en créant une stratégie d’étiquette](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

Pour plus d’informations sur l’utilisation des étiquettes de confidentialité avec les réunions, consultez [Utiliser des étiquettes de confidentialité pour protéger les éléments de calendrier, les réunions Teams et les conversations](/microsoft-365/compliance/sensitivity-labels-meetings).

## <a name="meeting-templates"></a>Modèles de réunion

Dans le niveau de protection *de base* , nous allons utiliser le modèle pour définir une valeur par défaut pour qui peut contourner la salle d’attente qui inclut des participants externes de domaines approuvés.

Nous empêcherons également les personnes qui composent par téléphone de contourner la salle d’attente. Vous pouvez omettre ce paramètre si votre organisation organise fréquemment des réunions où les participants rendez-vous doivent être en mesure de participer directement. S’il existe certains types de réunions où cela est vrai, envisagez d’utiliser un modèle distinct pour ces réunions.

Si vous avez choisi de désactiver les filigranes et le chiffrement de bout en bout dans la sensibilité, vous pouvez également utiliser le modèle pour masquer ces paramètres à l’organisateur de la réunion.

Pour créer un modèle de réunion personnalisé

1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Modèles de réunion**.
1. Sélectionnez **Ajouter.**
1. Tapez un nom et une description pour le modèle.
1. Dans la section **Appliquer une étiquette de confidentialité** , choisissez l’étiquette que vous avez créée ci-dessus.
1. Sélectionnez **Appliquer l’étiquette de confidentialité**, puis **verrouiller**.
1. Dans la liste déroulante **Salle d’attente** , sélectionnez **Tout le monde dans mon organisation, les organisations approuvées et les invités**.
1. Assurez-vous **que Personnes appel sur mon téléphone peut contourner la salle d’attente** est défini sur **Désactivé**, puis sélectionnez-la et sélectionnez **Verrouiller**.
1. Si vous avez désactivé les filigranes et le chiffrement de bout en bout avec l’étiquette de confidentialité, envisagez de sélectionner ces paramètres ici et de sélectionner **Masquer** afin que les organisateurs de la réunion ne les voient pas.
1. Modifiez les paramètres supplémentaires si vous le souhaitez.
1. Pour empêcher l’organisateur de la réunion de modifier un paramètre, sélectionnez-le, puis **sélectionnez Verrouiller**.
1. Pour empêcher l’organisateur de la réunion de voir un paramètre, sélectionnez-le, puis **sélectionnez Masquer**.
1. Sélectionnez **Enregistrer**.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble pour les réunions sensibles](meeting-templates-sensitivity-labels-policies.md)
