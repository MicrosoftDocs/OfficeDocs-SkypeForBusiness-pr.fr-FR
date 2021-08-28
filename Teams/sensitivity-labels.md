---
title: Étiquettes de sensibilité pour Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser des étiquettes de sensibilité pour protéger vos équipes dans Microsoft Teams.
ms.openlocfilehash: d00ebe1861596ddb41e852c7e8fe6360df024ab7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621956"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Étiquettes de sensibilité pour Microsoft Teams

[Les étiquettes de sensibilité](/microsoft-365/compliance/sensitivity-labels) permettent Teams administrateurs de protéger et de réguler l’accès au contenu organisationnel sensible créé lors de la collaboration au sein d’équipes. Après avoir configuré les étiquettes de confidentialité avec les stratégies associées dans le Centre de conformité [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)ces étiquettes peuvent être appliquées aux équipes de votre organisation.

Les étiquettes de sensibilité ne sont actuellement pas pris en compte dans les équipes de classe pour les clients qui Teams S SKUs Éducation. Pour en savoir plus sur les licences, consultez[Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>Quelle est la différence entre les étiquettes de sensibilité et Teams de classification ?

Les étiquettes de sensibilité sont différentes des étiquettes de classification, également appelées classification de groupe Azure AD. Les étiquettes de classification sont des chaînes de texte qui peuvent être associées à Microsoft 365 groupe de personnes, mais qui n’ont aucune stratégie réelle associée. Les étiquettes de classification sont des métadonnées, puis vous devez utiliser d’autres méthodes, telles que des outils et scripts internes, pour appliquer des stratégies.

L’utilisation d’étiquettes de confidentialité permet d’appliquer automatiquement leurs stratégies de bout en bout via une combinaison de la plateforme Microsoft 365 Groups, du centre de conformité et des services Teams. Les étiquettes de confidentialité fournissent une prise en charge puissante de l’infrastructure pour sécuriser les données sensibles de votre organisation et assurer le respect de vos politiques ou réglementations internes.

Si vous utilisez actuellement des étiquettes de classification, consultez la documentation suivante pour plus d’informations et des instructions sur leur migration vers des étiquettes de sensibilité : Classification de groupe [Azure AD classique.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)

## <a name="example-scenarios-for-sensitivity-labels"></a>Exemples de scénarios pour les étiquettes de sensibilité

Exemples de scénarios d’utilisation d’étiquettes de sensibilité avec des Teams dans votre organisation :

- [Définir le niveau de confidentialité (public ou privé) pour les équipes](#set-the-privacy-level-for-teams)
- [Contrôler l’accès invité aux équipes](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Définir le niveau de confidentialité des équipes

Vous pouvez créer et configurer une étiquette de confidentialité qui, lorsqu’elle est appliquée lors de la création de l’équipe, permet aux utilisateurs de créer des équipes avec un paramètre de confidentialité spécifique (public ou privé).

Par exemple, vous créez et publiez une étiquette de confidentialité nommée « Confidentiel » qui a l’option de confidentialité de l’étiquette configurée comme **Privée.** Par conséquent, toute équipe créée avec cette étiquette doit être privée. 

Lorsqu’un utilisateur crée une équipe  et sélectionne l’étiquette Confidentiel, la seule option de confidentialité disponible pour l’utilisateur est **Privé.** D’autres options de confidentialité, telles que Publique et À l’échelle de l’organisation, ne peuvent pas être sélectionnées par l’utilisateur :

![Capture d’écran de l’étiquette confidentiel](media/sensitivity-labels-confidential-example.png)

De même, vous créez et publiez une étiquette de confidentialité nommée « Général » dont l’option de confidentialité de l’étiquette est configurée en tant que **Public.** Lorsqu’un utilisateur crée une équipe, il ne peut créer des équipes publiques ou à l’échelle de l’organisation que s’ils sélectionnent cette étiquette :

![Capture d’écran de l’étiquette de sensibilité Général](media/sensitivity-labels-general-example.png)

Lorsque l’équipe est créée, l’étiquette de sensibilité est visible dans le coin supérieur droit des canaux de l’équipe. 

> [!NOTE]
> Si vous utilisez des étiquettes hiérarchiques de type parent-enfant, telles que « Confidentiel\Finance », seule l’étiquette du parent s’affiche dans l’en-tête du canal.

![Capture d’écran de l’étiquette de sensibilité dans le canal d’équipe](media/sensitivity-labels-channel.png)

Un propriétaire d’équipe peut modifier l’étiquette de confidentialité et le paramètre de confidentialité de l’équipe à tout moment en se rendre à l’équipe, puis en cliquant **sur Modifier l’équipe.**

![Capture d’écran de l’étiquette de sensibilité dans les propriétés de l’équipe](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Contrôler l’accès invité aux équipes

Vous pouvez utiliser des étiquettes de sensibilité pour contrôler l’accès invité à vos équipes. Teams’étiquette qui n’autorise pas l’accès invité sont uniquement disponibles pour les utilisateurs de votre organisation. Des personnes extérieures à votre organisation ne peuvent pas être ajoutées à l’équipe.

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams d’administration

Vous pouvez appliquer des étiquettes de sensibilité lorsque vous créez ou modifiez une équipe dans le Microsoft Teams d’administration. 

Les étiquettes de sensibilité sont également visibles dans les propriétés de l’équipe et dans la colonne **Classification** de la **page** Gérer les équipes du Microsoft Teams d’administration.

## <a name="limitations"></a>Limites

Avant d’utiliser des étiquettes de sensibilité Teams, faites attention aux limitations suivantes :

- **Les noms des étiquettes parents ne sont pas affichés pour les sous-étiquettes**
    
    Teams prend en charge les sous-titres, mais n’affiche pas le nom de l’étiquette parente. Par exemple, **Confidentiel** \\ **tous les employés s’affiche** comme Tous les **employés.**

- **Les étiquettes de sensibilité ne sont pas pris en charge Teams Graph API, les cmdlets PowerShell et les modèles**
    
    Les utilisateurs ne peuvent pas spécifier d’étiquettes de sensibilité lors de la création d’équipes directement via Teams Graph API, Teams cmdlets PowerShell et Teams modèles. Toutefois, les Graph api et cmdlets PowerShell permettent la création de groupes avec des étiquettes. Les utilisateurs peuvent donc créer des groupes avec des étiquettes à l’aide de Graph API ou d’cmdlets PowerShell, puis convertir ces groupes en Teams.

- **Prise en charge des canaux privés**
    
    Les canaux privés créés dans une équipe héritent de l’étiquette de sensibilité appliquée à une équipe. La même étiquette est appliquée automatiquement sur la SharePoint collection de sites pour le canal privé.
    
    Toutefois, si un utilisateur modifie directement l’étiquette de sensibilité d’un site SharePoint pour un canal privé, cette modification n’est pas reflétée dans le client Teams privé. Dans ce scénario, les utilisateurs continuent à voir l’étiquette de sensibilité d’origine appliquée à l’équipe dans l’en-tête du canal privé.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Comment créer et configurer des étiquettes de sensibilité pour Teams

Utilisez les instructions de la documentation Microsoft 365 pour créer et configurer des étiquettes de sensibilité pour Teams : 

- Utilisez des étiquettes de sensibilité pour protéger le contenu [Microsoft Teams, Microsoft 365 groupes et SharePoint sites.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)
