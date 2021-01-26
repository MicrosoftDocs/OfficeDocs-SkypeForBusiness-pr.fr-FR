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
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980448"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Placer un utilisateur ou une équipe Microsoft Teams en conservation légale
==================================================

Lorsqu’il existe une attente raisonnable en matière de litige, les organisations sont tenues de conserver électroniquement les informations stockées (ESI), y compris les messages de conversation Teams pertinents pour un cas particulier. Les organisations doivent conserver tous les messages liés à un sujet spécifique ou à certaines personnes. Cet article traite de la mise en attente légale dans Microsoft Teams (Pour résoudre le problème de mise en œuvre des contenus dans l’espace M365, consultez l’article Gérer les cas de découverte électronique : Mettre les emplacements de contenu [en attente).)](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)

> [!NOTE]
> En février 2020, nous avons activé la tenue légale ou la conversation de cas sur des canaux privés (les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, les conversations de canal normales sont stockées dans la boîte aux lettres de groupe d’une équipe). Si une boîte aux lettres utilisateur est déjà en place, la stratégie de confidentialité s’applique désormais automatiquement aux messages de canal privé stockés dans cette boîte aux lettres. Aucune action supplémentaire n’est requise pour qu’un administrateur l’activer. La propriété légale des fichiers partagés dans des canaux privés est également prise en charge.

Dans Microsoft Teams, une équipe entière ou des utilisateurs sélectionnés peuvent être mis en attente ou mis en attente légale. Cela permet de s’assurer que tous les messages échangés dans ces équipes (y compris les canaux privés) ou les messages échangés par ces personnes sont découvrons par les responsables de la conformité de l’organisation ou les administrateurs Teams.

> [!NOTE]
> Placer un utilisateur en conservation n'implique pas automatiquement le placement d'un groupe en conservation, et inversement.

Pour placer un utilisateur ou une équipe en attente légale :

1. Accédez au [Centre de & sécurité et conformité.](https://go.microsoft.com/fwlink/?linkid=854628) Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

2. Allez à eDiscovery ou Advanced eDiscovery et créez un cas en cliquant sur « Créer un cas ». Une fois le cas créé, ouvrez-le.

   > [!div class="mx-imgBorder"]
   > ![L’onglet eDiscovery de Microsoft Teams est sélectionné et affiche le bouton Créer un cas.](media/LegalHold1.png)

3. Dans le menu supérieur, dans la section « En attente », cliquez sur « + Créer » pour créer une attente. Mettre un utilisateur ou une équipe en attente enregistre tous les messages échangés par ces utilisateurs ou messages. Lorsque vous créez un cas, la possibilité de placer des boîtes aux lettres ou des sites en attente s’offre à vous.

   > [!div class="mx-imgBorder"]
   > ![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)

   1. **Nommez votre attente.** Sélectionnez un nom descriptif et unique pour la hold que vous allez créer.

      > [!div class="mx-imgBorder"]
      > ![Cette capture d’écran montre l’onglet Nommer votre attente, dans lequel vous pouvez entrer un nom et une description pour la hold-in que vous créez.](media/LegalHold3.png)

    2. **Choisissez un emplacement.** Choisissez si vous souhaitez appliquer la attente à un utilisateur ou à une équipe entière (le hold ne peut pas être appliqué à des canaux individuels pour l’instant). Remarque : si un utilisateur est en attente, tous ses messages sont en attente, y compris les messages envoyés dans une conversation à deux, une conversation à deux ou de groupe ou une conversation de canal (y compris les canaux privés).
  
       > [!div class="mx-imgBorder"]
       > ![Vous avez ici la section Choisir des emplacements de Créer une nouvelle attente, dans laquelle vous pouvez prendre des décisions sur les options M365, y compris Microsoft Teams, à laquelle vous souhaitez que la attente s’applique.](media/LegalHold4.png)

    3. **Créer une requête.** Vous pouvez personnaliser le hold si vous souhaitez plus de granularité dans la stratégie de hold. Par exemple, vous pouvez spécifier des mots clés à rechercher ou ajouter des conditions, qui doivent être satisfaites pour que la attente prenne effet.
    
    4. **Examinez vos paramètres** avant de les publier dans votre organisation.

Une fois la rétention légale définie, vous pouvez découvrir tout le contenu conservé par une stratégie de rétention à la suite de l’article [eDiscovery Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Lorsqu’un utilisateur ou un groupe est mis en attente, toutes les copies des messages sont conservées. Par exemple, si un utilisateur a publié un message dans un canal, puis l’a modifié, dans un scénario de mise en attente, les deux copies du message sont conservées. Sans la rétention légale sur place, seul le dernier message est conservé.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Emplacements de contenu à placer en conservation légale afin de conserver le contenu de Teams

À titre de guide utile, vous pouvez utiliser le tableau suivant pour comprendre quel emplacement de contenu (par exemple, une boîte aux lettres ou un site) placer en conservation légale afin de conserver différents types de contenu teams.

|Scénario  |Emplacement du contenu  |
|---------|---------|
|Conversations Teams pour un utilisateur (par exemple, des conversations 1:1, des conversations de groupe 1:N et des conversations de canal privé)     |Boîte aux lettres utilisateur.         |
|Conversations de canal Teams (à l’exception des canaux privés)    |Boîte aux lettres du groupe utilisée pour l’équipe.         |
|Contenu de fichier Teams (par exemple, contenu wiki et fichiers)     |Site SharePoint utilisé par l’équipe.         |
|Fichiers de canal privé Teams     |Site SharePoint dédié pour les canaux privés.     |
|Contenu privé de l’utilisateur     |Le compte OneDrive Entreprise de l’utilisateur.         |
|Contenu de la carte dans les conversations|Boîte aux lettres utilisateur pour les conversations en tête-à-tête, les conversations de groupe en tête-à-tête et les conversations de canal privé ou la boîte aux lettres de groupe pour le contenu de la carte dans les messages de canal. Pour plus d’informations, voir la section « Conserver le contenu de la carte » dans Créer une [conservation eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Pour conserver les communications dans les canaux privés, vous devez mettre les boîtes aux lettres des utilisateurs (utilisateurs de canaux privés) en attente et, lorsque vous utilisez l’outil eDiscovery pour effectuer une recherche, vous devez effectuer une recherche dans la boîte aux lettres de cet utilisateur. Comme indiqué précédemment, les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, et non dans la boîte aux lettres de groupe d’une équipe.

Si vous souhaitez consulter davantage d’informations sur les zones autres que Teams dans Microsoft 365, consultez l’rubrique Gérer les cas de découverte électronique : mettre les emplacements de contenu [en attente.](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)
