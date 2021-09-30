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
description: Découvrez comment placer un utilisateur ou une équipe Microsoft Teams en conservation légale à l'aide du Centre de sécurité et de conformité et quels sont les éléments nécessaires à une conservation légale en fonction des données requises.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace4098b56539408e8c29e5d16e43c8ae255f372
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013348"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Placer un utilisateur ou une équipe Microsoft Teams en conservation légale

Lorsqu’une attente raisonnable concernant un litige existe, les organisations doivent conserver électroniquement des informations stockées (ESI), Teams messages de conversation pertinents pour un cas particulier. Les organisations doivent conserver tous les messages liés à un sujet spécifique ou à certaines personnes. Cet article traite de la Microsoft Teams. Pour conserver du contenu Microsoft 365, voir [Créer une hold eDiscovery.](/microsoft-365/compliance/create-ediscovery-holds)

> [!NOTE]
> En février 2020, nous avons désactivé l’action légale pour les canaux privés. Les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, tandis que les conversations de canal normales sont stockées dans la boîte aux lettres Teams groupe de l’utilisateur. Si une boîte aux lettres utilisateur est déjà en place, la stratégie de confidentialité s’applique désormais automatiquement aux messages de canal privé stockés dans cette boîte aux lettres. Aucune action supplémentaire n’est requise pour qu’un administrateur l’activer. La propriété légale des fichiers partagés dans des canaux privés est également prise en charge.

Dans Microsoft Teams, une équipe entière ou des utilisateurs sélectionnés peuvent être mis en attente légale. Cela permet de s’assurer que tous les messages échangés dans ces équipes (y compris les canaux privés) ou les messages échangés par ces personnes sont découvrons par les responsables de la conformité ou les administrateurs de l’Teams de l’organisation.

> [!NOTE]
> Placer un utilisateur en conservation n'implique pas automatiquement le placement d'un groupe en conservation, et inversement.
> Les notifications envoyées dans le flux d’activités ne peuvent pas être mises en attente.

Pour placer un utilisateur ou une équipe en attente légale dans un cas de découverte électronique principal :

1. Allez à la [Centre de conformité Microsoft 365.](https://compliance.microsoft.com) Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

2. Allez à **eDiscovery**  >  **Core** et créez un cas en cliquant **sur Créer un cas.** Une fois le cas créé, ouvrez-le.
  
   ![Microsoft Teams’onglet eDiscovery est sélectionné, affichant le bouton Créer un cas.](media/LegalHold1.png)

   > [!NOTE]
   > Vous pouvez également placer un utilisateur en attente associé à Advanced eDiscovery cas. Pour plus d’informations, voir [Gérer les Advanced eDiscovery.](/microsoft-365/compliance/managing-holds)

3. Dans le menu **supérieur,** sous l’onglet Attentes, cliquez **sur** Créer pour créer une attente. Le placement en attente d’un utilisateur ou d’une équipe conserve tous les messages échangés par ces utilisateurs ou messages. Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

   ![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)
    
    1. **Nommez votre attente.** Sélectionnez un nom descriptif et unique pour la hold que vous allez créer.
  
       ![Cette capture d’écran montre l’onglet Nommer votre attente, dans lequel vous pouvez entrer un nom et une description pour la hold-in que vous créez.](media/LegalHold3.png)

    1. **Choisissez un emplacement.** Choisissez si vous souhaitez appliquer la attente à un utilisateur ou à une équipe entière (le hold ne peut pas être appliqué à des canaux individuels pour l’instant). Remarque : si un utilisateur est en attente, tous ses messages sont en attente, y compris les messages envoyés dans une conversation à deux, une conversation à deux ou de groupe ou une conversation de canal (y compris les canaux privés).
    ![Voici la section Choisir des emplacements de Créer une nouvelle attente, dans laquelle vous pouvez prendre des décisions sur les options M365, y compris les Microsoft Teams, à laquelle vous souhaitez que la attente s’applique.](media/LegalHold4.png)

    2. **Créer une requête.** Vous pouvez personnaliser le hold si vous souhaitez plus de granularité dans la stratégie de hold. Par exemple, vous pouvez spécifier des mots clés à rechercher ou ajouter des conditions, qui doivent être satisfaites pour que la attente prenne effet.
    
    3. **Examinez vos paramètres** avant de créer la mise en attente.

Une fois la rétention légale créée, vous pouvez effectuer une recherche dans le contenu conservé par n’importe quelle stratégie de rétention. Pour plus d’informations, [voir Effectuer une enquête de découverte électronique dans Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Lorsqu’un utilisateur ou un groupe est mis en attente, toutes les copies des messages sont conservées. Par exemple, si un utilisateur a publié un message dans un canal, puis l’a modifié, dans un scénario de mise en attente, les deux copies du message sont conservées. Sans la rétention légale sur place, seul le dernier message est conservé.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Emplacements de contenu à placer en conservation légale afin de conserver Teams contenu

À titre de guide utile, vous pouvez utiliser le tableau suivant pour comprendre quel emplacement de contenu (par exemple, une boîte aux lettres ou un site) placer en conservation légale afin de conserver différents types Teams contenu.

|Scénario  |Emplacement du contenu  |
|---------|---------|
|Teams conversations pour un utilisateur (par exemple, des conversations 1:1, des conversations de groupe 1:N et des conversations de canal privé)     |Boîte aux lettres utilisateur.         |
|Teams conversations de canal (à l’exception des canaux privés)    |Boîte aux lettres du groupe utilisée pour l’équipe.         |
|Teams contenu du fichier (par exemple, du contenu wiki et des fichiers)     |SharePoint site utilisé par l’équipe.         |
|Teams fichiers de canal privé     |Site dédié SharePoint pour les canaux privés.     |
|Contenu privé de l’utilisateur     |Le compte de l’OneDrive Entreprise utilisateur.         |
|Contenu de la carte dans les conversations|Boîte aux lettres utilisateur pour les conversations en tête-à-tête, les conversations de groupe en tête-à-tête et les conversations de canal privé ou la boîte aux lettres de groupe pour le contenu de la carte dans les messages de canal. Pour plus d’informations, voir la section « Conserver le contenu de la carte » dans Créer une [conservation eDiscovery.](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)|


> [!NOTE]
> Pour conserver les communications dans les canaux privés, vous devez mettre les boîtes aux lettres des utilisateurs (utilisateurs de canaux privés) en attente et, lorsque vous utilisez l’outil eDiscovery pour effectuer une recherche, vous devez effectuer une recherche dans la boîte aux lettres de cet utilisateur. Comme indiqué précédemment, les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, et non dans la boîte aux lettres de groupe d’une équipe.

Si vous souhaitez consulter davantage d’informations sur les aspects non Teams dans Microsoft 365, consultez l’rubrique Gérer les cas de découverte électronique : mettre les emplacements de contenu en [attente.](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)
