---
title: Placer un utilisateur ou une équipe Microsoft Teams en conservation légale
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment placer un utilisateur Microsoft Teams ou une équipe en attente légale à l’aide du Centre de conformité Microsoft 365 et ce qui nécessite une attente légale basée sur les exigences relatives aux données.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711558"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Placer un utilisateur ou une équipe Microsoft Teams en conservation légale

Lorsqu’il existe des attentes raisonnables en cas de litige, les organisations sont tenues de conserver électroniquement les informations stockées (ESI), Teams messages de conversation pertinents pour ce cas. Les organisations peuvent avoir besoin de conserver tous les messages relatifs à une investigation spécifique ou à une personne en particulier. Cet article décrit l’utilisation d’une conservation légale pour conserver le contenu Microsoft Teams. Pour conserver le contenu d’autres services Microsoft 365, voir [Créer une conservation eDiscovery](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> En février 2020, nous avons désactivé l’action légale pour les canaux privés. Les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, tandis que les conversations de canal standard sont stockées dans la boîte aux lettres associée à l’équipe parente. Si une boîte aux lettres utilisateur est déjà conservée, la stratégie de hold-in s’applique désormais automatiquement aux messages de canal privé stockés dans cette boîte aux lettres. Aucune autre action n’est requise pour qu’un administrateur l’activer. La propriété légale des fichiers partagés dans des canaux privés est également prise en charge.

Dans Microsoft Teams, une équipe entière ou des utilisateurs sélectionnés peuvent être mis en attente légale. Cela permet de s’assurer que tous les messages échangés dans ces équipes (y compris les canaux privés et partagés) ou les messages échangés par ces personnes sont découvrons par les responsables de la conformité ou les administrateurs de l’entreprise Teams personnel.

> [!NOTE]
> Placer un utilisateur en conservation n'implique pas automatiquement le placement d'un groupe en conservation, et inversement.
> Les notifications envoyées dans les flux d’activités ne peuvent pas être mises en attente.

Pour placer un utilisateur ou une équipe en attente légale dans un cas de découverte électronique principal :

1. Allez à la [Centre de conformité Microsoft 365](https://compliance.microsoft.com). Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

2. Allez à **eDiscoveryCore** >  et créez un cas en cliquant **sur Créer un cas**. Une fois le cas créé, ouvrez-le.
  
   ![Microsoft Teams’onglet eDiscovery est sélectionné et affiche le bouton Créer un cas.](media/LegalHold1.png)

   > [!NOTE]
   > Vous pouvez également placer un utilisateur en attente associé à Advanced eDiscovery cas. Pour plus d’informations, [voir Gérer les Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Dans **l’onglet En** attente du menu supérieur, cliquez sur **Créer pour créer** une attente. Le placement en attente d’un utilisateur ou d’une équipe conserve tous les messages échangés par ces utilisateurs. Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

   ![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)

   1. **Nommez votre attente**. Sélectionnez un nom descriptif et unique pour la hold que vous allez créer.
  
       ![Cette capture d’écran montre l’onglet Nommer votre attente, dans lequel vous pouvez entrer un nom et une description pour la hold-in que vous créez.](media/LegalHold3.png)

   2. **Choisissez un emplacement**. Choisissez si vous souhaitez appliquer la attente à un utilisateur ou à une équipe entière (une attente ne peut pas être appliquée à des canaux individuels pour le moment). Si un utilisateur est en attente, tous ses messages sont conservés, y compris les messages dans les conversations en tête-à-tête, les conversations de groupe et les canaux privés. Les messages dans les canaux standard et partagés sont conservés lorsque l’équipe parente est mise en attente.

      ![Choisissez les emplacements de données à mettre en attente.](media/LegalHold4.png)

   3. **Créer une requête**. Vous pouvez personnaliser le hold si vous souhaitez plus de granularité dans la stratégie de hold. Par exemple, vous pouvez spécifier des mots clés à rechercher ou vous pouvez ajouter des conditions, qui doivent être satisfaites pour que la attente prenne effet.

   4. **Examinez vos paramètres** avant de créer la mise en attente.

Une fois la rétention créée, vous pouvez effectuer une recherche dans le contenu conservé par la stratégie de rétention. Pour plus d’informations, [voir Effectuer une enquête de découverte électronique dans Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Lorsqu’un utilisateur ou un groupe est mis en attente, toutes les copies de conformité des messages sont conservées. Par exemple, si un utilisateur publie un message dans un canal, puis modifie le message, les deux copies du message sont conservées. Sans la conservation, seul le dernier message est conservé.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Emplacements de contenu à placer en attente pour conserver Teams contenu

Pour vous aider à comprendre les emplacements de contenu (par exemple, une boîte aux lettres ou un site) à mettre en attente afin de conserver différents types Teams contenu, le tableau suivant vous guide.

|Scénario  |Emplacement du contenu  |
|---------|---------|
|Messages de conversation pour un utilisateur (par exemple, conversations 1:1, conversations de groupe 1:N et conversations de canal privé)     |Boîte aux lettres de l'utilisateur         |
|Messages de conversation dans les canaux standard et partagés    |Boîte aux lettres associée à l’équipe parent         |
|Fichiers dans des canaux standard (par exemple, du contenu wiki et des fichiers)     |SharePoint site associé à l’équipe parente        |
|Fichiers dans les canaux privés et partagés     |Site SharePoint dédié associé au canal
|Contenu privé de l’utilisateur     |Compte d’utilisateur OneDrive Entreprise’utilisateur       |
|Contenu de la carte dans les conversations|Boîte aux lettres utilisateur pour les conversations en tête-à-tête, les conversations de groupe en tête-à-tête et les conversations de canal privé ; boîte aux lettres de l’équipe parente pour le contenu de la carte dans les messages de canal standard et partagés ; Pour plus d’informations, voir la section « Conserver le contenu de la carte » dans [Créer une conservation eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Pour conserver le contenu des messages dans des canaux privés, vous devez mettre en attente les boîtes aux lettres des utilisateurs (des membres d’un canal privé). et lorsque vous utilisez l’outil eDiscovery pour effectuer une recherche dans les messages de canal privé, vous devez effectuer une recherche dans la boîte aux lettres de l’utilisateur. Comme indiqué précédemment, les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, et non dans la boîte aux lettres de groupe associée à l’équipe parente.
