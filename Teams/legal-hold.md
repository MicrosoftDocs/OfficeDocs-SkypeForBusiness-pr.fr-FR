---
title: Placer un utilisateur ou une équipe Microsoft Teams en conservation légale
description: Découvrez comment placer un utilisateur ou une équipe Microsoft Teams en attente légale à l’aide de la portail de conformité Microsoft Purview et découvrir ce qui nécessite une conservation légale en fonction des exigences en matière de données.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- tier1
- purview-compliance
- M365-collaboration
- ediscovery
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78dcc82c6a02cc702527f2653da131bdb52c8775
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047064"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Placer un utilisateur ou une équipe Microsoft Teams en conservation légale

Lorsqu’il existe une attente raisonnable de litige, les organisations doivent conserver les informations stockées électroniquement (ESI), y compris les messages de conversation Teams pertinents pour le cas. Les organisations peuvent avoir besoin de conserver tous les messages liés à une enquête spécifique ou à une personne spécifique. Cet article traite de l’utilisation d’une conservation légale pour préserver le contenu dans Microsoft Teams. Pour conserver du contenu dans d’autres services dans Microsoft 365, consultez [Créer une conservation eDiscovery](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> En février 2020, nous avons activé la suspension légale pour les chaînes privées. Les conversations de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, tandis que les conversations de canal standard sont stockées dans la boîte aux lettres associée à l’équipe parente. S’il existe déjà une conservation légale pour une boîte aux lettres utilisateur, la stratégie de conservation s’applique désormais automatiquement aux messages de canal privé stockés dans cette boîte aux lettres. Aucune autre action n’est nécessaire pour qu’un administrateur active cette option. La conservation légale des fichiers partagés dans des canaux privés est également prise en charge.

Dans Microsoft Teams, toute une équipe ou certains utilisateurs peuvent être mis en attente légale. Cela permet de s’assurer que tous les messages échangés dans ces équipes (y compris les canaux privés et partagés) ou les messages échangés par ces personnes sont détectables par les responsables de conformité de l’organisation ou les administrateurs Teams.

> [!NOTE]
> Placer un utilisateur en conservation n'implique pas automatiquement le placement d'un groupe en conservation, et inversement.
> Les notifications envoyées dans les flux d’activité ne peuvent pas être mises en attente.

Pour mettre un utilisateur ou une équipe en conservation légale dans un cas eDiscovery (Standard) :

1. Accédez à la [portail de conformité Microsoft Purview](https://compliance.microsoft.com). Lorsque vous créez un cas, vous avez la possibilité de mettre des boîtes aux lettres ou des sites en attente.

2. Accédez à **eDiscovery** > **Core** et créez un cas en cliquant sur **Créer un cas**. Une fois le cas créé, ouvrez-le.
  
   ![L’onglet Microsoft Teams eDiscovery est sélectionné, affichant le bouton Créer un cas.](media/LegalHold1.png)

   > [!NOTE]
   > Vous pouvez également placer un utilisateur en attente associé à un cas eDiscovery (Premium). Pour plus d’informations, consultez [Gérer les conservations dans eDiscovery (Premium).](/microsoft-365/compliance/managing-holds)

3. Accédez à l’onglet **Conservations** dans le menu supérieur, puis cliquez sur **Créer** pour créer une conservation. La mise en attente d’un utilisateur ou d’une équipe préserve tous les messages échangés par ces utilisateurs. Lorsque vous créez un cas, vous avez la possibilité de mettre des boîtes aux lettres ou des sites en attente.

   ![Image montrant l’onglet Conservations sélectionné et le bouton Créer en dessous.](media/LegalHold2.png)

   1. **Nommez votre conservation**. Sélectionnez un nom descriptif et unique pour la conservation que vous allez créer.
  
       ![Cette capture d’écran montre l’onglet Nom de votre conservation, dans lequel vous pouvez entrer un nom et une description pour la conservation que vous créez.](media/LegalHold3.png)

   2. **Choisissez l’emplacement**. Choisissez si vous souhaitez que la suspension soit appliquée à un utilisateur ou à une équipe entière (une conservation ne peut pas être appliquée sur des canaux individuels pour l’instant). Si un utilisateur est en attente, tous ses messages sont conservés, y compris les messages dans les conversations 1:1, les conversations de groupe et les canaux privés. Les messages dans les canaux standard et partagés sont conservés lorsque l’équipe parente est mise en attente.

      ![Choisissez les emplacements de données que vous souhaitez mettre en attente.](media/LegalHold4.png)

   3. **Créez une requête**. Vous pouvez personnaliser la conservation si vous souhaitez plus de granularité dans la stratégie de conservation. Par exemple, vous pouvez spécifier des mots clés à rechercher ou ajouter d’autres conditions qui doivent être satisfaites pour que la suspension prenne effet.

   4. **Passez en revue vos paramètres** avant de créer la conservation.

Une fois la conservation créée, vous pouvez rechercher le contenu conservé par la stratégie de conservation. Pour plus d’informations, consultez [Effectuer une enquête eDiscovery dans Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Lorsqu’un utilisateur ou un groupe est mis en attente, toutes les copies de conformité des messages sont conservées. Par exemple, si un utilisateur publie un message dans un canal, puis modifie le message, les deux copies du message sont conservées. Sans conservation, seul le dernier message est conservé.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Emplacements de contenu à mettre en attente pour conserver le contenu Teams

Pour vous aider, utilisez le tableau suivant pour comprendre quels emplacements de contenu (par exemple, une boîte aux lettres ou un site) doivent être mis en attente pour conserver différents types de contenu Teams.

|Scénario  |Emplacement du contenu  |
|---------|---------|
|Messages de conversation pour un utilisateur (par exemple, conversations 1:1, conversations de groupe 1:N et conversations de canal privé)     |Boîte aux lettres de l'utilisateur         |
|Messages de conversation dans les canaux standard et partagés    |Boîte aux lettres associée à l’équipe parente         |
|Fichiers dans des canaux standard (par exemple, contenu wiki et fichiers)     |Site SharePoint associé à l’équipe parente        |
|Fichiers dans des canaux privés et partagés     |Site SharePoint dédié associé au canal
|Contenu privé de l’utilisateur     |Compte OneDrive Entreprise de l’utilisateur       |
|Contenu de la carte dans les conversations|Boîte aux lettres utilisateur pour les conversations 1:1, les conversations de groupe 1:N et les conversations de canal privé ; boîte aux lettres de l’équipe parente pour le contenu de la carte dans les messages de canal standard et partagés. Pour plus d’informations, consultez la section « Conserver le contenu de la carte » dans [Créer une conservation eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Pour conserver le contenu des messages dans les canaux privés, vous devez mettre les boîtes aux lettres utilisateur (des membres d’un canal privé) en attente. et lorsque vous utilisez l’outil eDiscovery pour rechercher des messages de canal privé, vous devez effectuer une recherche dans la boîte aux lettres de l’utilisateur. Comme indiqué précédemment, les conversations de canal privé sont stockées dans des boîtes aux lettres utilisateur, et non dans la boîte aux lettres de groupe associée à l’équipe parente.
