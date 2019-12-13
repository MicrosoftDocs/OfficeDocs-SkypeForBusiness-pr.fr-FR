---
title: Étiquettes de confidentialité de Microsoft teams
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment définir et utiliser des étiquettes de sensibilité dans Microsoft Teams.
ms.openlocfilehash: 899bf8c3dc187df6fa5e035817458a10330c66a6
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002318"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Étiquettes de confidentialité de Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Les [étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permettent aux administrateurs d’équipes de réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes. Vous pouvez définir des étiquettes de sensibilité et leurs politiques associées dans le [Centre de sécurité & conformité](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center). Celles-ci s’appliquent automatiquement aux équipes au sein de votre organisation.  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Quelle est la différence entre les étiquettes de sensibilité et les étiquettes de classification d’équipe ?

Les étiquettes de sensibilité diffèrent des étiquettes de classification qui nécessitent que vous les créez à l’aide de PowerShell. Les étiquettes de classification sont des chaînes de texte qui peuvent être associées à un groupe, mais qui ne sont associées à aucune stratégie réelle. Vous utilisez des étiquettes de classification en tant que métadonnées pour appliquer manuellement des stratégies par le biais d’outils et de scripts internes.

En revanche, les étiquettes de sensibilité et leurs politiques sont automatiquement appliquées de bout en bout par le biais d’une combinaison de la plateforme de groupes, du centre de sécurité & de conformité et des services d’équipe. Les étiquettes de sensibilité fournissent un puissant support d’infrastructure pour la sécurisation des données sensibles de votre organisation.  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>Créer, gérer et publier des étiquettes de confidentialité pour teams

Pour plus d’informations sur l’activation, la création et la publication d’étiquettes de sensibilité pour les équipes, voir [utiliser des étiquettes de sensibilité avec Microsoft Teams, les groupes Office 365 et les sites SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

>[!IMPORTANT]
>La création, la mise à jour et la suppression d’étiquettes de sensibilité nécessitent un séquençage rigoureux avec des étiquettes de publication aux utilisateurs. Tout écart dans la séquence peut entraîner des erreurs de création d’équipe persistantes pour tous les utilisateurs. Par conséquent, il est essentiel de procéder comme suit pour <a href="#createpublishlabels">créer et publier des étiquettes</a>, <a href="#modifydeletelabels">modifier et supprimer des étiquettes publiées</a>et <a href="#manageerrors">gérer les erreurs de création d’équipe</a>.

**Créer et publier des étiquettes** <a name="createpublishlabels"></a>

Lors de la création et de la publication d’une étiquette dans le centre de sécurité & conformité, il peut s’écouler jusqu’à 24 heures avant que l’étiquette s’affiche dans l’interface de création d’équipes. Procédez comme suit pour publier l’étiquette de tous les utilisateurs du client :
1. Créez l’étiquette et publiez-la pour quelques comptes d’utilisateurs sélectionnés dans le client.
2. Une fois l’étiquette publiée, attendez 24 heures.
3. Après 24 heures, essayez de créer une équipe avec l’étiquette à l’aide de l’un des comptes d’utilisateurs qui ont accès à l’étiquette.
4. Si l’équipe a été créée à l’étape 3, continuez et publiez l’étiquette pour les utilisateurs restants dans le client.

**Modification et suppression d’étiquettes publiées** <a name="modifydeletelabels"></a>

La suppression ou la modification de l’étiquette alors qu’elle est associée aux stratégies de confidentialité peut entraîner des échecs de création d’équipe sur le client. Par conséquent, avant de supprimer ou de modifier une étiquette, vous devez d’abord dissocier l’étiquette de ses stratégies associées. Procédez comme suit  
pour supprimer ou modifier une étiquette :
1. Supprimez l’étiquette de toutes les stratégies utilisant l’étiquette. Vous pouvez également supprimer les stratégies eux-mêmes.
2. Lorsque l’étiquette est supprimée des stratégies ou que les stratégies lui-même sont supprimées, attendez 48 heures avant de continuer.
3. Après 48 heures, lancez l’interface de création d’équipe et assurez-vous que l’étiquette n’est plus visible pour les utilisateurs du client.
4. Vous pouvez maintenant supprimer ou modifier l’étiquette en toute sécurité.

**Gérer les erreurs** <a name="manageerrors"></a> de création d’équipe

Si la création d’une équipe commence à échouer à tout moment pendant la préversion publique, deux options s’offrent à vous :
 - Assurez-vous que les étiquettes de sensibilité ne sont pas obligatoires pour les utilisateurs lors de la création d’une équipe.
 - Désactivez les étiquettes de sensibilité en utilisant les scripts de l’option [activer cet aperçu](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).

Notez que le paramètre EnableMIPLabels doit être défini sur false comme suit :

```
$setting["EnableMIPLabels"] = "False"
 ```

## <a name="using-sensitivity-labels-with-teams"></a>Utilisation d’étiquettes de sensibilité avec teams

Voici quelques exemples illustrant comment utiliser les étiquettes de sensibilité avec les équipes au sein de votre organisation.

### <a name="privacy-setting-of-teams"></a>Paramètre de confidentialité de teams

Vous pouvez créer une étiquette de critère de diffusion qui, lorsqu’elle est appliquée au cours de la création d’une équipe, permet aux utilisateurs de créer des équipes ayant un paramètre de confidentialité (privée ou privée) spécifique.

Par exemple, vous créez une étiquette nommée « confidentiel » dans le centre de sécurité & conformité et vous configurez des équipes de sorte que toutes les équipes créées avec cette étiquette doivent être une équipe privée. Lorsqu’un utilisateur crée une nouvelle équipe et sélectionne l’étiquette **confidentiel** , la seule option de confidentialité disponible pour l’utilisateur est **privée**. D’autres options de protection de la vie privée, telles que le public et l’organisation, sont désactivées pour l’utilisateur.

![Capture d’écran d’une étiquette de confidentialité confidentiel](media/sensitivity-labels-confidential-example.png)

De même, si l’utilisateur sélectionne **général** lors de la création d’une équipe, il peut uniquement créer des équipes publiques ou à l’échelle de l’organisation.

![Capture d’écran d’une étiquette de critère de diffusion générale](media/sensitivity-labels-general-example.png)

Lors de la création de l’équipe, l’étiquette de sensibilité est visible dans le coin supérieur droit de la page canaux de l’équipe.

![Capture d’écran d’une étiquette de critère de diffusion dans un canal d’équipe](media/sensitivity-labels-channel.png)

Le propriétaire d’une équipe peut changer l’étiquette de diffusion et le paramètre de confidentialité de l’équipe à tout moment en accédant à l’équipe et en cliquant sur **modifier l’équipe**.

![Capture d’écran d’une étiquette de critère de diffusion dans un canal d’équipe](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>Accès invité aux équipes

Vous pouvez spécifier si une équipe créée avec une étiquette spécifique autorise l’accès invité. Les équipes créées avec une étiquette qui ne permet pas l’accès invité ne sont accessibles qu’aux utilisateurs de votre organisation. Les personnes externes à votre organisation ne peuvent pas être ajoutées à l’équipe.

## <a name="known-issues"></a>Problèmes connus

**Support pour les étiquettes de sensibilité dans le centre d’administration Microsoft teams**

Pour l’instant, les étiquettes de sensibilité ne sont pas prises en charge dans le centre d’administration Microsoft Teams. Si vous utilisez des étiquettes de sensibilité, vous ne pourrez pas définir les étiquettes de sensibilité lors de la création ou de la modification d’une équipe. Les étiquettes de sensibilité sont également invisibles dans les propriétés d’équipe et ne sont pas visibles dans la colonne **classification** du centre d’administration Microsoft Teams.

**Prise en charge des étiquettes de sensibilité dans les API du graphique Teams, les cmdlets PowerShell et les modèles**

Pour le moment, les utilisateurs ne seront pas en mesure d’appliquer des étiquettes de sensibilité aux équipes créées directement par le biais d’API de graphique, de cmdlets PowerShell et de modèles.

**Modification directe des étiquettes de sensibilité sur une collection de sites SharePoint pour les canaux privés**

Les canaux privés créés dans une équipe héritent de l’étiquette de sensibilité appliquée au sein d’une équipe. Par ailleurs, la même étiquette est appliquée automatiquement sur la collection de sites SharePoint pour le canal privé.

Si un utilisateur met à jour directement l’étiquette de critère de diffusion sur une collection de sites SharePoint pour un canal privé, cette étiquette n’est pas mise à jour dans le client Teams. Dans ce scénario, les utilisateurs continuent de voir l’étiquette de sensibilité appliquée à une équipe dans l’en-tête de canal privé.

**Temps de propagation des modifications appliquées aux étiquettes de sensibilité en dehors de l’application teams**

Les modifications apportées aux étiquettes de sensibilité en dehors de l’application teams peuvent prendre jusqu’à 24 heures pour refléter dans l’application Teams. Cela s’applique aux modifications apportées à l’activation ou à la désactivation d’étiquettes pour un client, aux modifications apportées aux noms des étiquettes, aux paramètres et aux stratégies.

De plus, les modifications apportées à une étiquette apportées directement à un groupe ou une collection de sites SharePoint qui stocke l’équipe peuvent prendre jusqu’à 24 heures avant d’être propagées à l’application Teams.
