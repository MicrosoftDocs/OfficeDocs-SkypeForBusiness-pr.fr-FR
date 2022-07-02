---
title: Utiliser Teams avec des services bureau à distance
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser Microsoft Teams avec des services bureau à distance.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606093"
---
# <a name="teams-in-remote-desktop-services"></a>Équipes dans les services Bureau à distance

Cet article décrit les exigences et limitations relatives à l’utilisation de Microsoft Teams dans un environnement de services bureau à distance (RDS).

## <a name="what-is-rds"></a>Qu’est-ce que RDS ?

Les services Bureau à distance (RDS) sont la plateforme de choix pour la création de solutions de virtualisation pour chaque besoin du client final. RdS vous permet de fournir des applications virtualisées individuelles, de fournir un accès sécurisé aux bureaux mobiles et à distance, et de fournir aux utilisateurs finaux la possibilité d’exécuter leurs applications et bureaux à partir du cloud.

RdS offre une flexibilité de déploiement, une rentabilité et une extensibilité. Les services Bureau à distance sont fournis par le biais de diverses options de déploiement, notamment Windows Server 2016 pour les déploiements locaux, Microsoft Azure pour les déploiements cloud et un tableau robuste de solutions de partenaires.
En fonction de votre environnement et de vos préférences, vous pouvez configurer la solution RDS pour la virtualisation basée sur une session, en tant qu’infrastructure de bureau virtuel (VDI)

Actuellement, Teams dans un environnement de services bureau à distance est disponible avec prise en charge des fonctionnalités de collaboration et de conversation. Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams sur les services Bureau à distance avec conversation et collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau de l’utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Centre d’administration Microsoft Teams ou de PowerShell. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas de modifications pour un compte donné immédiatement, réessayez dans quelques heures.

[**Polices d’appel**](teams-calling-policy.md) : Teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de réunion**](meeting-policies-overview.md) : Teams inclut la stratégie de réunion AllOff intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Microsoft Teams

Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff à un utilisateur :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en sélectionnant à gauche du nom d’utilisateur, puis **sélectionnez Modifier les paramètres**.
3. Procédez comme suit :

    a.  Sous **Stratégie d’appel**, sélectionnez **DisallowCalling**.

    b.  Sous **Stratégie de réunion**, sélectionnez **AllOff**.

4. Sélectionnez **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, sélectionnez la &#x2713; (coche) en haut du tableau.
3. Sélectionnez **Modifier les paramètres**, apportez les modifications **souhaitées, puis sélectionnez Appliquer**.

Vous pouvez également effectuer les étapes suivantes :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à la stratégie que vous souhaitez affecter. Par exemple :

    - Accédez aux **stratégies d’appel** **vocal** > , puis sélectionnez **DisallowCalling**.
    - Accédez aux **stratégies réunions** > , puis sélectionnez **AllOff**.

2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, **sélectionnez Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, consultez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).