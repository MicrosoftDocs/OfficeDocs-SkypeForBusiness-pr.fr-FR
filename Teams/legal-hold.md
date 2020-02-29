---
title: Placer un utilisateur ou une équipe Microsoft Teams en conservation légale
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment placer un utilisateur ou une équipe Microsoft Teams en conservation légale à l'aide du Centre de sécurité et de conformité et quels sont les éléments nécessaires à une conservation légale en fonction des données requises.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3727ac3f6b9ded4c3dbb34a1977f9b99cbaf15e
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341632"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Placer un utilisateur ou une équipe Microsoft Teams en conservation légale
==================================================

S’il existe une éventualité raisonnable de litige, les organisations doivent conserver les informations stockées électroniquement (ESI), y compris les messages de discussion de teams pertinents. Les organisations peuvent avoir besoin de conserver tous les messages relatifs à un sujet spécifique ou à certaines personnes. Cet article aborde la conservation légale dans Microsoft Teams (pour gérer la mise en attente de la mise en place de l’espace M365, consultez la rubrique [gérer les cas de découverte électronique : placer les emplacements de contenu en attente](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).)

> [!NOTE]
> En février 2020, nous avons activé le blocage légal ou la conservation des dossiers sur les canaux privés (les discussions de canal privé sont stockées dans les boîtes aux lettres des utilisateurs, les discussions de canal normales sont stockées dans les boîtes aux lettres de groupe de ces équipes). S’il existe déjà un blocage légal en vigueur pour une boîte aux lettres d’utilisateur, la stratégie de conservation s’applique désormais automatiquement aux messages de canal privé stockés dans cette boîte aux lettres. Aucune action supplémentaire n’est nécessaire pour qu’un administrateur active cette fonction. Le blocage légal des fichiers partagés dans les canaux privés est également pris en charge.

Dans Microsoft Teams, une équipe entière ou des utilisateurs peuvent être mis en attente ou en conservation légale. Cela permet de s’assurer que tous les messages échangés avec ces équipes (y compris les canaux privés) ou les messages échangés par ces personnes sont détectables par les responsables de la conformité ou par les administrateurs de l’organisation.

> [!NOTE]
> Placer un utilisateur en conservation n'implique pas automatiquement le placement d'un groupe en conservation, et inversement.

Pour mettre en attente un utilisateur ou une équipe en attente légale :

1. Accédez au [Centre de sécurité & conformité](https://go.microsoft.com/fwlink/?linkid=854628). Lorsque vous créez un nouveau cas, vous avez la possibilité de placer des boîtes aux lettres ou des sites en attente.
1. Accédez à eDiscovery ou Advanced eDiscovery et créez un cas en cliquant sur « + créer un cas ». Une fois la demande de création, ouvrez-la.
![L’onglet eDiscovery de Microsoft teams est sélectionné, avec le bouton créer un cas.](media/LegalHold1.png)
1. Dans le menu supérieur, accédez à la section « conservations », puis cliquez sur « + créer » pour créer un blocage le placement d’un utilisateur ou d’une équipe en attente enregistre tous les messages échangés par ces utilisateurs ou messages lorsque vous créez un nouveau cas, vous avez la possibilité de placer des boîtes aux lettres ou des sites en attente.
![Image montrant l’onglet conservations sélectionné et le bouton créer situé au-dessous.](media/LegalHold2.png)
    1. **Nommez votre conservation**. Sélectionnez un nom descriptif et unique pour l’attente que vous allez créer.
![Cette capture d’écran illustre le nom de votre onglet de conservation, dans lequel vous pouvez entrer un nom et une description pour l’attente que vous créez.](media/LegalHold3.png)
    1. **Sélectionnez emplacement**. Déterminez si vous voulez que la conservation soit appliquée à un utilisateur ou à une équipe entière (la conservation ne peut pas être appliquée aux canaux individuels pour le moment). Remarque : si un utilisateur est en attente, tous ses messages seront suspendus, y compris les éléments envoyés dans une conversation 1:1, 1 : plusieurs personnes ou conversations de groupe, ou une conversation de canal (y compris les canaux privés).
    ![Dans cette section, vous trouverez la section choisir des emplacements dans créer une nouvelle mise en attente, qui vous permet de prendre des décisions sur les options M365, notamment Microsoft Teams, auxquelles vous voulez que la conservation s’applique.](media/LegalHold4.png)
    1. **Créer une requête**. Vous pouvez personnaliser la conservation si vous souhaitez davantage de granularité dans la stratégie de suspension. Par exemple, vous pouvez spécifier des mots-clés à chercher ou ajouter des conditions supplémentaires qui doivent être satisfaites pour que la conservation soit appliquée.
    1. **Passez en revue vos paramètres** avant de le publier dans votre organisation.

Lorsque le maintien légal a été défini, vous pouvez découvrir tout le contenu conservé par n’importe quelle stratégie de conservation en suivant l’article [EDiscovery teams](eDiscovery-investigation.md) .

> [!IMPORTANT]
> Lorsqu’un utilisateur ou un groupe est suspendu, toutes les copies de messages sont conservées. Par exemple, si un utilisateur a publié un message dans un canal puis modifié le message, dans un scénario de conservation, les deux copies du message sont conservées. Sans le maintien légal sur place, seul le dernier message est conservé.

Pour vous aider, vous pouvez utiliser le tableau ci-dessous pour comprendre ce qui doit être placé sur le blocage légal en fonction de la configuration requise pour les données :

|Scénario  |Éléments à placer en conservation  |
|---------|---------|
|**Le contenu de Microsoft teams chat par un utilisateur (dans les discussions 1:1, 1 : plusieurs personnes ou discussions de groupe, conversations de canal privé, etc.)**     |Boîte aux lettres de l'utilisateur         |
|**Discussions de canal de Microsoft Teams (exclusion de canaux privés)**    |Boîte aux lettres de groupe utilisée pour l'équipe         |
|**Contenu de Microsoft Teams (par exemple, wiki, fichiers)**     |Site SharePoint utilisé par l'équipe         |
|**Fichiers de canaux privés de Microsoft teams**     |Site SharePoint dédié au canal privé     |
|**Contenu privé de l’utilisateur**     |Site OneDrive Entreprise de l'utilisateur         |

> [!NOTE]
> Pour conserver la communication dans les canaux privés, vous devez placer les boîtes aux lettres d’utilisateur (utilisateurs de canaux privés) en attente et, lors de l’utilisation de l’outil eDiscovery pour effectuer une recherche, vous devez effectuer une recherche dans la boîte aux lettres de l’utilisateur. Comme indiqué précédemment, les discussions de canal privé sont stockées dans les boîtes aux lettres d’utilisateur, pas dans la boîte aux lettres de groupe d’une équipe.

Pour en savoir plus sur ce sujet, consultez gérer les cas de découverte électronique dans M365, consultez la rubrique [gérer les cas de découverte électronique : placer les emplacements de contenu en attente](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).
