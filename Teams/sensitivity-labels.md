---
title: Étiquettes de confidentialité pour Microsoft Teams
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- tier1
- purview-compliance
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment utiliser des étiquettes de confidentialité pour protéger vos équipes dans Microsoft Teams.
ms.openlocfilehash: 59bd67ea59787a1f73b2a0c808bfa3464c3bc31b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046874"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Étiquettes de confidentialité pour Microsoft Teams

[Les étiquettes de confidentialité](/microsoft-365/compliance/sensitivity-labels) permettent aux administrateurs Teams de protéger et de réglementer l’accès au contenu organisationnel sensible créé lors de la collaboration au sein des équipes. Une fois que vous avez configuré des étiquettes de confidentialité avec leurs stratégies associées dans le [portail de conformité Microsoft Purview](/microsoft-365/compliance/go-to-the-securitycompliance-center), ces étiquettes peuvent être appliquées aux équipes de votre organisation.

Les étiquettes de confidentialité ne sont actuellement pas prises en charge dans les équipes de classe pour les clients utilisant des références SKU Teams Éducation. Pour en savoir plus sur les licences, consultez[Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>Quelle est la différence entre les étiquettes de confidentialité et la classification Teams ?

Les étiquettes de confidentialité sont différentes de la classification Teams, également appelée classification de groupe Azure AD. Les classifications sont des chaînes de texte qui peuvent être associées à un groupe Microsoft 365, mais qui n’ont aucune stratégie réelle associée. Vous utilisez la classification en tant que métadonnées, puis vous devez utiliser d’autres méthodes, telles que des outils et des scripts internes, pour appliquer des stratégies.

L’avantage de l’utilisation d’étiquettes de confidentialité est que leurs stratégies sont automatiquement appliquées de bout en bout par le biais d’une combinaison de la plateforme Groupes Microsoft 365, du portail de conformité Microsoft Purview et des services Teams. Les étiquettes de confidentialité fournissent une prise en charge puissante de l’infrastructure pour sécuriser les données sensibles de votre organisation et garantir la conformité avec vos stratégies ou réglementations internes.

Si vous utilisez actuellement la classification Teams, consultez la documentation suivante pour plus d’informations et des instructions sur la façon de convertir ces valeurs en étiquettes de confidentialité : [classification de groupe Azure AD classique](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

## <a name="example-scenarios-for-sensitivity-labels"></a>Exemples de scénarios pour les étiquettes de confidentialité

Voici des exemples de scénarios permettant d’utiliser des étiquettes de confidentialité avec Teams dans votre organisation :

- [Définir le niveau de confidentialité (public ou privé) pour les équipes](#set-the-privacy-level-for-teams)
- [Contrôler l’accès invité aux équipes](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>Définir le niveau de confidentialité pour les équipes

Vous pouvez créer et configurer une étiquette de confidentialité qui, lorsqu’elle est appliquée lors de la création de l’équipe, permet aux utilisateurs de créer des équipes avec un paramètre de confidentialité spécifique (public ou privé).

Par exemple, vous créez et publiez une étiquette de confidentialité nommée « Confidentiel » dont l’option de confidentialité d’étiquette est configurée comme **privée**. Par conséquent, toute équipe créée avec cette étiquette doit être une équipe privée. 

Lorsqu’un utilisateur crée une équipe et sélectionne l’étiquette **Confidentiel** , la seule option de confidentialité disponible pour l’utilisateur est **Private**. D’autres options de confidentialité telles que public et à l’échelle de l’organisation ne sont pas disponibles pour que l’utilisateur sélectionne :

![Capture d’écran de l’étiquette confidentialité.](media/sensitivity-labels-confidential-example.png)

De même, vous créez et publiez une étiquette de confidentialité nommée « Général » dont l’option de confidentialité d’étiquette est configurée en tant que **Public**. Lorsqu’un utilisateur crée une équipe, il peut uniquement créer des équipes publiques ou à l’échelle de l’organisation lorsqu’il sélectionne cette étiquette :

![Capture d’écran de l’étiquette de confidentialité générale.](media/sensitivity-labels-general-example.png)

Lorsque l’équipe est créée, l’étiquette de confidentialité est visible pour les utilisateurs dans le coin supérieur droit des canaux de l’équipe. 

![Capture d’écran de l’étiquette de confidentialité dans le canal d’équipe.](media/sensitivity-labels-channel.png)

Un propriétaire d’équipe peut modifier l’étiquette de confidentialité et le paramètre de confidentialité de l’équipe à tout moment en accédant à l’équipe, puis en cliquant sur **Modifier l’équipe**.

![Capture d’écran de l’étiquette de confidentialité dans les propriétés de l’équipe.](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>Contrôler l’accès invité aux équipes

Vous pouvez utiliser des étiquettes de confidentialité pour contrôler l’accès invité à vos équipes. Les équipes créées avec une étiquette qui n’autorise pas l’accès invité sont uniquement disponibles pour les utilisateurs de votre organisation. Personnes en dehors de votre organisation ne peuvent pas être ajoutées à l’équipe.

## <a name="microsoft-teams-admin-center"></a>Centre d’administration Microsoft Teams

Vous pouvez appliquer des étiquettes de confidentialité lorsque vous créez ou modifiez une équipe dans le Centre d’administration Microsoft Teams. Les étiquettes de confidentialité sont également visibles dans les propriétés de l’équipe et dans la colonne **Classification** de la page **Gérer les équipes** du Centre d’administration Microsoft Teams.

## <a name="limitations"></a>Limites

Avant d’utiliser des étiquettes de confidentialité pour Teams, tenez compte des limitations suivantes :

- **Les étiquettes de confidentialité ne sont pas prises en charge par les API Graph Teams et les applets de commande PowerShell**
    
    Les utilisateurs ne pourront pas spécifier d’étiquettes de confidentialité lors de la création d’équipes directement via les API Teams Graph ou les applets de commande Teams PowerShell. Toutefois, les API Graph de groupes modernes et les applets de commande PowerShell permettent la création de groupes avec des étiquettes de confidentialité. Cela signifie que vous pouvez créer des groupes avec des étiquettes de confidentialité à l’aide de ces méthodes, puis convertir ces groupes en équipes.

- **Prise en charge des canaux privés**
    
    Les canaux privés créés dans une équipe héritent de l’étiquette de confidentialité appliquée à une équipe. La même étiquette est appliquée automatiquement sur la collection de sites SharePoint pour le canal privé.
    
    Toutefois, si un utilisateur modifie directement l’étiquette de confidentialité sur un site SharePoint pour un canal privé, cette modification d’étiquette ne se reflète pas dans le client Teams. Dans ce scénario, les utilisateurs continuent à voir l’étiquette de confidentialité d’origine appliquée à l’équipe dans l’en-tête de canal privé.

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>Comment créer et configurer des étiquettes de confidentialité pour Teams

Suivez les instructions de la documentation Microsoft Purview pour créer et configurer des étiquettes de confidentialité pour Teams : 

- [Utilisez des étiquettes de confidentialité pour protéger le contenu dans Microsoft Teams, les groupes Microsoft 365 et les sites SharePoint](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).
