---
title: Gérer les stratégies de rétention pour Microsoft Teams
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Utilisez les stratégies de rétention de Microsoft Teams pour conserver les messages nécessaires au respect des stratégies internes, réglementations du secteur, ou obligations légales, et supprimer les messages qui sont considérés comme passifs ou qui n’ont aucune valeur commerciale légale.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6c370eee74266d2d24df4fa8e1e95904cd08386
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711288"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a>Gérer les stratégies de rétention pour Microsoft Teams

> [!NOTE]
> Si vous voyez dans Teams un message concernant la suppression de vos conversations ou messages par une stratégie de rétention, consultez [Messages Teams à propos des stratégies de rétention](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Les informations figurant sur cette page sont destinées aux administrateurs informatiques qui gèrent ces stratégies de rétention.

Les stratégies de rétention et étiquettes de rétention de Microsoft 365 vous aident à gérer les informations au niveau de votre organisation plus efficacement. Vous pouvez configurer des paramètres de rétention pour conserver des données nécessaires au respect des stratégies internes, réglementations du secteur, ou obligations légales de votre organisation. Vous pouvez également configurer des paramètres de rétention pour supprimer les données considérées comme étant des responsabilités, que vous n’êtes plus tenu de conserver ou qui n’ont plus de valeur juridique ou commerciale.

En tant qu’administrateur, Teams prend en charge les stratégies de rétention pour les messages de conversation et de canal de sorte que, en tant qu’administrateur, vous pouvez décider de conserver ces données de façon proactive, de les supprimer ou de les conserver pendant une période spécifique, puis de les supprimer. Le début de la période de rétention de ces actions est toujours basé sur la création d’un message. Vous pouvez appliquer une stratégie de rétention Teams à l’ensemble de votre organisation ou à des utilisateurs et des équipes spécifiques. Les étiquettes de rétention ne sont pas prise en charge pour Teams.

> [!NOTE]
> [Les canaux partagés](shared-channels.md), actuellement en prévisualisation, sont désormais pris en charge par les stratégies de rétention.

Pour plus d’informations sur les solutions de rétention dans Microsoft 365, consultez [En savoir plus sur les stratégies de rétention et les étiquettes de rétention](/microsoft-365/compliance/retention).

Les utilisateurs soumis à une stratégie de rétention pour Teams doivent disposer d’une licence appropriée, telle qu’Office 365 E3 ou Office 365 A3. Pour obtenir d’autres options de licence pour ces stratégies de rétention, consultez la section [Gestion des informations](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) à partir de [Conseils de gestion des licences pour la sécurité et la conformité de Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance). Pour en savoir plus sur les licences Teams, consultez[Description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a>Prise en charge des actions de rétention et de suppression par les stratégies de rétention Teams

Si vous configurez une stratégie de rétention Teams pour conserver des conversations ou des messages de canal, les utilisateurs peuvent toujours modifier et supprimer leurs messages dans leur application Teams. Bien que les utilisateurs ne voient plus leurs messages pré-modifiés ou supprimés dans Teams, les données de ces messages sont stockées dans un emplacement sécurisé conçu pour les recherches eDiscovery par les administrateurs de conformité. La suppression définitive de ces données ne se produit pas avant la fin de la période de rétention configurée, ou si une autre stratégie de rétention est configurée pour conserver ces données, ou si elle est soumise à une [conservation eDiscovery](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).

Lorsqu’une stratégie de rétention est configurée pour supprimer des conversations et des messages de canal, ces messages peuvent être supprimés automatiquement. Si les messages sont toujours affichés dans l’application Teams, ils disparaissent de là et les [utilisateurs sont informés qu’une stratégie de rétention a supprimé ces messages](#end-user-experience). Si les messages étaient précédemment soumis à une action de rétention et ont été modifiés ou supprimés par des utilisateurs, ces messages seront désormais supprimés de l’emplacement sécurisé et ne seront plus renvoyés dans les recherches eDiscovery.

Pour plus d’informations sur le fonctionnement de ces stratégies en fonction de votre configuration de stratégies et des actions d’utilisateur, ainsi que les données de messages incluses ou exclues des stratégies de rétention Teams, consultez [En savoir plus sur la rétention de Microsoft Teams](/microsoft-365/compliance/retention-policies-teams). Cette page vous explique pourquoi on constate parfois des retards lorsque des stratégies de rétention suppriment des messages. Par exemple, les messages peuvent être consultés par les utilisateurs 7 jours après la période d’expiration que vous avez configurée dans la stratégie de rétention.

Si vous définissez plusieurs stratégies de rétention Teams avec des paramètres de rétention différents, les principes de rétention résoudront les éventuels conflits. Par exemple :

- En cas de conflit entre la conservation ou la suppression du même contenu, le contenu est toujours conservé dans l’emplacement sécurisé afin qu’il reste consultable avec eDiscovery pour les administrateurs de conformité.
    
    Ce principe s’applique également aux messages soumis à des conservations eDiscovery pour des raisons juridiques ou d’investigation.

- S’il existe un conflit relatif à la durée de rétention du même contenu, il est conservé pendant la période de rétention la plus longue dans l’emplacement sécurisé.

Ces deux principes de rétention s’adressent à la plupart des conflits qui peuvent survenir lorsque vous avez plusieurs stratégies de rétention pour Teams. Pour plus d’informations, consultez [Principes de rétention et priorités ?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)

## <a name="when-to-use-retention-policies-for-teams"></a>Quand utiliser les politiques de conservation pour Teams

Dans de nombreux cas, les organisations considèrent les données de conversation privé plus comme une responsabilité que les messages de canal, qui sont généralement des conversations plus liées au projet.

Vous pouvez configurer très efficacement une stratégie de rétention unique pour tous Teams messages. Pour un contrôle plus fin, vous pouvez également :

- Avoir des stratégies de rétention distinctes pour les conversations privées (conversations 1:1 ou 1:1: plusieurs), les messages provenant de canaux standard ou les messages de canaux privés.

- Appliquez les stratégies uniquement à des utilisateurs ou équipes spécifiques de votre organisation. Pour Teams conversations et canaux privés, vous pouvez sélectionner les utilisateurs pour lesquels la stratégie s’applique. Pour les conversations Teams, vous pouvez sélectionner les équipes auxquels la stratégie s’applique.

Par exemple, pour les messages de canal standard : Créer une stratégie de rétention pour des équipes spécifiques de votre organisation et configurer cette stratégie avec une action de suppression après un an. Ensuite, créez une autre stratégie de rétention pour les messages de canal standard pour toutes les autres équipes et configurez cette stratégie avec une action de suppression au bout de 3 ans.

## <a name="create-and-manage-retention-policies-for-teams"></a>Créer et gérer des stratégies de rétention pour Teams

Pour créer ou modifier une stratégie de rétention pour Teams messages électroniques, utilisez les instructions de la stratégie de rétention [pour Teams emplacements.](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)

Cette page présente des informations supplémentaires sur la création et la gestion des stratégies de rétention pour d’autres charges de travail dans Microsoft 365. Par exemple, vous pouvez également créer une stratégie de rétention pour les groupes Microsoft 365 afin de conserver et de supprimer les fichiers accessibles dans Teams et qui sont stockés dans OneDrive ou SharePoint.  

## <a name="end-user-experience"></a>Expérience de l’utilisateur final

Pour les conversations privées (conversations en tête à tête) ou de groupe, les utilisateurs constatent que les conversations plus anciennes que la configuration de la stratégie de rétention sont supprimées, et un message généré automatiquement affichant « Nous avons supprimé d’anciens messages en raison de la stratégie de rétention de votre organisation » en haut des messages encore non supprimés. Par exemple :

:::image type="content" source="media/retention-policies-image1.png" alt-text="Un utilisateur est informé Teams message de conversation sont supprimés en raison d’une stratégie Teams rétention.":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Les utilisateurs Teams expliquant les messages sont supprimés à la suite d’une stratégie Teams rétention.":::

Pour les messages de canal, les utilisateurs (membres du canal) voient les messages supprimés disparaître de l’affichage à l’expiration des messages. Si le message supprimé était un message parent d’une conversation à thread, un message indiquant « Ce message a été supprimé en raison d’une stratégie de rétention » s’affiche à la place du message parent. Par exemple :

:::image type="content" source="media/retention-policies-image3.png" alt-text="Capture d’écran du canal avant la rétention.":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="Capture d’écran du canal après la rétention.":::

> [!NOTE]
> Pour l’instant, les messages affichés qui résultent de la suppression ne sont pas configurables.

Les liens dans ces messages affichés sont disponibles dans [messages Teams concernant les stratégies de rétention](https://support.microsoft.com/en-us/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b). Cette documentation pour les utilisateurs finaux répond aux questions de base sur la raison pour laquelle leurs messages ont été supprimés. Toutefois, dans le cadre du déploiement de votre stratégie de rétention, veillez à communiquer aux utilisateurs et au service d’aide l’impact de vos paramètres configurés.

## <a name="related-topics"></a>Rubriques connexes

- [Prise en main des stratégies et des étiquettes de rétention](/microsoft-365/compliance/get-started-with-retention)
- [En savoir plus sur la rétention dans Microsoft Teams](/microsoft-365/compliance/retention-policies-teams)
- [Créer et configurer des stratégies de rétention](/microsoft-365/compliance/create-retention-policies)
