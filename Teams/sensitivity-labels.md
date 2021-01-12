---
title: Étiquettes de sensibilité pour Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment définir et utiliser des étiquettes de sensibilité dans Microsoft Teams.
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795772"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Étiquettes de sensibilité pour Microsoft Teams

[Les étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permettent aux administrateurs Teams de réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes. Vous pouvez définir des étiquettes de confidentialité et les stratégies associées dans [le Centre de conformité.](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center) Ces étiquettes et stratégies sont automatiquement appliquées aux équipes de votre organisation.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Quelle est la différence entre les étiquettes de sensibilité et les étiquettes de classification Teams ?

Les étiquettes de sensibilité sont différentes des étiquettes de classification. Les étiquettes de classification sont des chaînes de texte qui peuvent être associées à un groupe Microsoft 365, mais qui ne sont associées à aucune stratégie réelle. Les étiquettes de classification sont des métadonnées qui vous aideront à appliquer manuellement les stratégies au moyen d’outils et de scripts internes.

En revanche, les étiquettes de confidentialité et leurs stratégies sont automatiquement appliquées de bout en bout via une combinaison de la plateforme Groups, du Centre de sécurité & conformité et des services Teams. Les étiquettes de sensibilité fournissent une prise en charge puissante de l’infrastructure pour sécuriser les données sensibles de votre organisation.  

Pour migrer vos groupes existants de l’utilisation d’étiquettes de classification à l’utilisation d’étiquettes de sensibilité, utilisez les instructions dans la classification et les étiquettes de sensibilité Azure Active Directory pour les groupes [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Créer, gérer et publier des étiquettes de sensibilité pour Teams

Pour savoir comment activer, créer et publier des étiquettes de sensibilité pour Teams, voir Utiliser des étiquettes de sensibilité pour protéger le contenu dans Microsoft Teams, des groupes [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)et des sites SharePoint.

>[!IMPORTANT]
>La création, la mise à jour et la suppression d’étiquettes de sensibilité nécessitent une planification minutieuse des étiquettes de publication auprès des utilisateurs. Tout écart de la séquence peut entraîner des erreurs permanentes de création d’équipe pour tous les utilisateurs. Par conséquent, il est essentiel de <a href="#createpublishlabels"></a>suivre les étapes suivantes lorsque vous créez et publiez des étiquettes, modifiez et supprimez les étiquettes publiées, <a href="#modifydeletelabels"></a>et gérez les erreurs de création <a href="#manageerrors">d’équipe.</a>

**Créer et publier des étiquettes** <a name="createpublishlabels"></a>

Lorsqu’une étiquette est créée et publiée dans le Centre de conformité, jusqu’à 10 minutes peuvent être avant d’être visibles dans l’interface de création d’équipes. Pour publier l’étiquette pour tous les utilisateurs du client, utilisez les étapes suivantes :
1. Créez l’étiquette et publiez-la pour quelques comptes d’utilisateurs sélectionnés dans le client.
2. Une fois l’étiquette publiée, patientez 10 minutes.
3. Après 10 minutes, essayez de créer une équipe avec l’étiquette à l’aide de l’un des comptes d’utilisateur qui ont accès à l’étiquette.
4. Si l’équipe a été créée à l’étape 3, publiez l’étiquette pour les autres utilisateurs du client.

**Modifier et supprimer les étiquettes publiées** <a name="modifydeletelabels"></a>

La suppression ou la modification de l’étiquette associée à des stratégies de confidentialité peut entraîner des échecs de création d’équipe dans le client. Par conséquent, avant de supprimer ou de modifier une étiquette, vous devez d’abord dissocier l’étiquette des stratégies associées. Utilisez les étapes suivantes  
pour supprimer ou modifier une étiquette :
1. Supprimez l’étiquette de toutes les stratégies qui l’utilisent. Vous pouvez également supprimer les stratégies elles-mêmes.
2. Lorsque l’étiquette est supprimée des stratégies ou des stratégies elles-mêmes, attendez 10 minutes avant de poursuivre.
3. Après 10 minutes, lancez l’interface de création d’équipe et assurez-vous que l’étiquette n’est plus visible pour les utilisateurs du client.
4. Vous pouvez désormais supprimer ou modifier l’étiquette en toute sécurité.

**Gérer les erreurs de création d’équipe** <a name="manageerrors"></a>

Si la création d’équipe commence à échouer à tout moment pendant la prévisualisation publique, vous avez deux options :
 - Assurez-vous que les étiquettes de sensibilité ne sont pas obligatoires pour les utilisateurs lors de la création de l’équipe.
 - Désactiver les étiquettes de sensibilité à l’aide des scripts [dans Activer cette prévisualisation.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)

Notez que le paramètre EnableMIPLabels doit être réglé sur false comme suit :

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>Utilisation d’étiquettes de sensibilité avec Teams

Voici quelques exemples d’utilisation d’étiquettes de sensibilité avec Teams dans votre organisation.

### <a name="privacy-setting-of-teams"></a>Paramètre de confidentialité des équipes

Vous pouvez créer une étiquette de confidentialité qui, lorsqu’elle est appliquée lors de la création de l’équipe, permet aux utilisateurs de créer des équipes avec un paramètre de confidentialité spécifique (public ou privé).

Par exemple, vous créez une étiquette nommée « Confidentiel » dans le Centre de conformité & de sécurité et vous configurez Teams de telle sorte que toute équipe créée avec cette étiquette soit une équipe privée. Lorsqu’un utilisateur crée une équipe  et sélectionne l’étiquette Confidentiel, la seule option de confidentialité disponible pour l’utilisateur est **Privé.** D’autres options de confidentialité, telles que Publique et À l’échelle de l’organisation, sont désactivées pour l’utilisateur.

![Capture d’écran de l’étiquette confidentiel](media/sensitivity-labels-confidential-example.png)

De même, si l’utilisateur sélectionne Général lorsqu’il crée une équipe, il peut uniquement créer des équipes publiques ou à l’échelle de l’organisation. 

![Capture d’écran de l’étiquette de sensibilité Général](media/sensitivity-labels-general-example.png)

Lorsque l’équipe est créée, l’étiquette de sensibilité est visible dans le coin supérieur droit des canaux de l’équipe.

![Capture d’écran de l’étiquette de sensibilité dans le canal d’équipe](media/sensitivity-labels-channel.png)

Un propriétaire d’équipe peut modifier l’étiquette de confidentialité et le paramètre de confidentialité de l’équipe à tout moment en se rendre à l’équipe, puis en cliquant sur **Modifier l’équipe.**

![Capture d’écran de l’étiquette de sensibilité dans les propriétés de l’équipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Accès invité aux équipes

Vous pouvez spécifier si une équipe créée avec une étiquette spécifique autorise l’accès invité. Les équipes créées avec une étiquette qui n’autorise pas l’accès invité sont uniquement disponibles pour les utilisateurs de votre organisation. Des personnes extérieures à votre organisation ne peuvent pas être ajoutées à l’équipe.

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Étiquettes de sensibilité dans le Centre d’administration Microsoft Teams

Vous pouvez définir des étiquettes de sensibilité lorsque vous créez ou modifiez une équipe dans le Centre d’administration Microsoft Teams. Les étiquettes de sensibilité sont également visibles dans les propriétés des équipes et dans la colonne **Classification** de la page Gérer les équipes du Centre d’administration Microsoft Teams.

## <a name="known-issues"></a>Problèmes connus

**Prise en charge des étiquettes de sensibilité dans les API Teams Graph, les cmdlets PowerShell et les modèles**

Actuellement, les utilisateurs ne peuvent pas appliquer d’étiquettes de sensibilité sur les équipes qui sont créées directement via des API Graph, des cmdlets PowerShell et des modèles.

**Prise en charge des étiquettes de sensibilité dans les S SKU Teams EDU**

Les étiquettes de sensibilité ne sont actuellement pas pris en compte pour les clients qui utilisent les S SKUs Teams Éducation.

**Modification des étiquettes de sensibilité directement sur une collection de sites SharePoint pour les canaux privés**

Les canaux privés créés dans une équipe héritent de l’étiquette de sensibilité appliquée à une équipe. Par ailleurs, la même étiquette est appliquée automatiquement sur la collection de sites SharePoint pour le canal privé.

Si un utilisateur met directement à jour l’étiquette de sensibilité sur une collection de sites SharePoint pour un canal privé, cette étiquette n’est pas mise à jour dans le client Teams. Dans ce scénario, les utilisateurs continueront à voir l’étiquette de sensibilité appliquée à une équipe dans l’en-tête d’un canal privé.

**Temps de propagation des modifications appliquées aux étiquettes de sensibilité en dehors de l’application Teams**

La prise en compte des modifications apportées aux étiquettes de sensibilité en dehors de l’application Teams peut prendre jusqu’à 24 heures dans l’application Teams. Cela s’applique aux modifications apportées pour activer ou désactiver les étiquettes d’un client, les modifications apportées aux noms d’étiquettes, aux paramètres et aux stratégies.

En outre, toutes les modifications apportées à une étiquette qui ont été apportées directement à un groupe ou à une collection de sites SharePoint qui dos l’équipe peuvent prendre jusqu’à 24 heures pour être propagées à l’application Teams.
