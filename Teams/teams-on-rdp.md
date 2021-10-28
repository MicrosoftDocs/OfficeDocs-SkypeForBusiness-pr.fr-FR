---
title: Utiliser des Teams avec les services Bureau à distance
author: cichur
ms.author: serdars
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser des Microsoft Teams avec les services Bureau à distance.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8250991790b6fc2e326a31829e8afc3f8659df74
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605570"
---
# <a name="teams-in-remote-desktop-services"></a>Teams dans les Services Bureau à distance

Cet article décrit les exigences et les limitations relatives à l’utilisation de Microsoft Teams dans un environnement de services Bureau à distance.

## <a name="what-is-rds"></a>Qu’est-ce que les rds ?

Les services Bureau à distance sont la plateforme de choix pour créer des solutions de virtualisation pour chaque client final. Les services Bureau à distance vous permettent de fournir des applications virtualisées individuelles, d’accéder au bureau mobile et à distance sécurisés et de fournir aux utilisateurs finaux la possibilité d’exécuter leurs applications et bureaux à partir du cloud.

Les services RdS offrent une flexibilité, une efficacité de coût et une extensibilité du déploiement. Les services Bureau à jour sont disponibles via diverses options de déploiement, notamment des Windows Server 2016 pour les déploiements locaux, des Microsoft Azure pour les déploiements dans le cloud et un vaste éventail de solutions partenaires.
En fonction de votre environnement et de vos préférences, vous pouvez configurer la solution rds pour la virtualisation basée sur les sessions, en tant qu’infrastructure VDI (Virtual Desktop Infrastructure).

Pour le moment, Teams dans un environnement de services Bureau à distance est disponible avec la prise en charge de la collaboration et de la fonctionnalité de conversation. Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams sur les rds avec la conversation et la collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Microsoft Teams d’administration de l’entreprise ou de PowerShell. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau dans quelques heures.

[**Polices d’appel**](teams-calling-policy.md): Teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de**](meeting-policies-overview.md)réunion : Teams inclut la stratégie de réunion AllOff intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide Microsoft Teams centre d’administration

Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff à un utilisateur :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez à **Utilisateurs.**
2. Sélectionnez l’utilisateur en sélectionnant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres.**
3. Pour ce faire, vous pouvez :

    a.  Sous **Stratégie d’appel,** **sélectionnez DisallowCalling.**

    b.  Sous **Stratégie de réunion,** **sélectionnez AllOff.**

4. Sélectionnez **Appliquer.**

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, sélectionnez la &#x2713; (coche) en haut du tableau.
3. Sélectionnez **Modifier les paramètres,** a apporter les modifications de votre choix, puis **sélectionnez Appliquer.**

Vous pouvez également suivre les étapes suivantes :

1. Dans le navigation gauche du Microsoft Teams d’administration, allez à la stratégie que vous voulez attribuer. Par exemple :

    - Allez à **la**  >  **stratégie d’appel** vocal, puis **sélectionnez DisallowCalling.**
    - Allez dans **stratégies**  >  **de réunion Réunions,** puis **sélectionnez AllOff.**

2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **Enregistrer.**

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)

L’exemple suivant montre comment utiliser la stratégie de réunion [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)