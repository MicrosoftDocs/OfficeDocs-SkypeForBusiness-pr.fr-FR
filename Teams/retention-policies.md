---
title: Stratégies de conservation dans Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Utilisez des stratégies de rétention pour Microsoft Teams pour conserver les messages nécessaires au respect des stratégies internes, réglementations du secteur ou obligations légales, et pour supprimer les messages qui sont considérés comme une responsabilité ou qui n’ont pas de valeur juridique.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aba9858466b43693603aa4a1cd396748d2c83d6e
ms.sourcegitcommit: def4b475b785a7b963f499cf9a1044e842ff66a5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49786826"
---
# <a name="retention-policies-in-microsoft-teams"></a>Stratégies de conservation dans Microsoft Teams

Les stratégies de rétention et étiquettes de rétention de Microsoft 365 vous aident à gérer plus efficacement les informations de votre organisation. Vous pouvez configurer les paramètres de rétention pour conserver les données nécessaires pour se conformer aux stratégies internes, aux réglementations du secteur ou aux obligations légales de votre organisation. Vous pouvez également configurer les paramètres de rétention pour supprimer les données considérées comme étant responsables, que vous n’êtes plus tenu de conserver ou qui n’ont aucune valeur juridique ou professionnelle.

Teams prend en charge les stratégies de rétention pour les messages de conversation et de canal de sorte qu’en tant qu’administrateur, vous pouvez décider de façon proactive de conserver ces données, de les supprimer ou de les conserver pendant une période spécifique, puis de les supprimer. Vous pouvez appliquer une stratégie de conservation Teams à l’ensemble de votre organisation ou à des utilisateurs et des équipes spécifiques. Les étiquettes de rétention ne sont pas pris en charge pour Teams.

Pour en savoir plus sur la rétention et la manière d’appliquer des paramètres de rétention à l’aide de stratégies de rétention ou d’étiquettes de rétention pour d’autres charges de travail dans Microsoft 365, voir En savoir plus sur les stratégies de rétention et les étiquettes de [rétention.](https://docs.microsoft.com/microsoft-365/compliance/retention)

La licence minimale requise pour les stratégies de rétention pour Teams est Microsoft 365 E3. Pour en savoir plus sur les licences, consultez [la description du service Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="how-teams-retention-policies-work"></a>Fonctionnement des stratégies de conservation Teams

Les messages de conversation Teams sont stockés dans un dossier masqué dans la boîte aux lettres de chaque utilisateur inclus dans la conversation, et les messages de canal Teams sont stockés dans un dossier masqué similaire dans la boîte aux lettres de groupe pour l’équipe. Pour conserver les messages qui sont soumis à une stratégie de rétention, une copie du contenu est automatiquement conservée dans un dossier masqué nommé **Éléments récupérables.**  Tant que ces messages n’ont pas été supprimés définitivement du dossier NommésSi, ils restent accessibles dans les outils eDiscovery.

Pour plus d’informations sur les stratégies de rétention Teams incluses et exclues, et le fonctionnement de ces stratégies en fonction de votre configuration de stratégie, consultez En savoir plus sur la rétention [dans Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)

> [!NOTE]
> Cette page explique pourquoi les stratégies de rétention peuvent parfois retarder la suppression de messages. Par exemple, les messages peuvent être visibles jusqu’à 7 jours après la période d’expiration que vous avez configurée dans la stratégie de rétention.

Si vous avez installé plusieurs stratégies de rétention Teams avec des paramètres de rétention différents, les principes de rétention résolvent les conflits. Par exemple :
- En cas de conflit entre la rétention et la suppression d’un même contenu, le contenu est toujours conservé.
- En cas de conflit dans la durée de conservation du même contenu, il est conservé pendant la période de rétention la plus longue.

Ces deux principes de rétention s’adressent à la plupart des conflits qui peuvent survenir lorsque vous avez plusieurs stratégies de rétention pour Teams, mais pour plus d’informations, consultez les principes de rétention ou quelle stratégie prend le pas [?](https://docs.microsoft.com/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quand utiliser les politiques de conservation pour Teams

Dans de nombreux cas, les organisations considèrent les données de conversation privé plus comme une responsabilité que les messages de canal, qui sont généralement des conversations plus liées au projet.

Vous pouvez configurer des stratégies de conservation distinctes pour les conversations privées (1:1 ou 1 : plusieurs conversations) et les messages de canal. Vous pouvez également configurer des stratégies uniques qui s'appliquent à des utilisateurs ou des équipes spécifiques de votre organisation. Pour les conversations Teams, vous pouvez sélectionner les utilisateurs auxquels la stratégie s’applique. Pour les conversations Teams, vous pouvez sélectionner les équipes auxquels la stratégie s’applique.

Par exemple, pour les messages de canal, vous pouvez appliquer une stratégie de suppression d’un an à des équipes spécifiques au sein de votre organisation et appliquer une stratégie de suppression de trois ans à toutes les autres équipes.

## <a name="create-and-manage-retention-policies-for-teams"></a>Créer et gérer des stratégies de rétention pour Teams

Pour créer une stratégie de rétention pour les conversations et les messages de canal Teams, utilisez les instructions de la stratégie de [rétention pour les emplacements Teams.](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Cette page présente des informations supplémentaires sur la création et la gestion de stratégies de rétention pour d’autres charges de travail dans Microsoft 365. Par exemple, vous pouvez également créer une stratégie de rétention pour les groupes Microsoft 365 afin de conserver et de supprimer les fichiers accessibles dans Teams et stockés dans OneDrive ou SharePoint.  

## <a name="end-user-experience"></a>Expérience utilisateur final

Pour les conversations privées (conversations en tête-à-tête) ou de groupe, les utilisateurs finaux voient que les conversations plus anciennes que la configuration de la stratégie de rétention sont supprimées et un message de contrôle indiquant « Nous avons supprimé d’anciens messages en raison de la stratégie de rétention de votre organisation » s’affiche en haut des messages encore non supprimés.

:::image type="content" source="media/retention-policies-image1.png" alt-text="Utilisateur informé dans Teams que le message de conversation est supprimé en raison d’une stratégie de rétention Teams":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Un utilisateur dans Teams expliquant que les messages sont supprimés à la suite d’une stratégie de rétention Teams":::

Pour les messages de canal, les utilisateurs finaux (membres du canal) voient les messages supprimés disparaître de l’affichage une fois les messages expirés. Si le message supprimé était un message parent d’une conversation à thread, un message indiquant « Ce message a été supprimé en raison d’une stratégie de rétention » s’affiche à la place du message parent.

:::image type="content" source="media/retention-policies-image3.png" alt-text="Capture d’écran du canal avant la rétention":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Capture d’écran du canal après la rétention":::

> [!NOTE]
> Les messages affichés qui sont affichés par les utilisateurs finaux suite à la suppression de messages ne sont pas configurables pour le moment.


## <a name="related-topics"></a>Sujets associés

- [Prendre en main les stratégies de rétention et les étiquettes de rétention](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-retention)
- [En savoir plus sur la rétention dans Microsoft Teams](https://docs.microsoft.com/microsoft-365/compliance/retention-policies-teams)
- [Créer et configurer des stratégies de rétention](https://docs.microsoft.com/microsoft-365/compliance/create-retention-policies)