---
title: Parcage et récupération d’appel dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Découvrez comment utiliser le parc d’appels et récupérer pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: 9092e76b9d8db5e29c1dd5881cd6b0f69d70ae4a
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249506"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcage et récupération d’appel dans Microsoft Teams

La fonctionnalité Parcer et récupérer des appels permet à un utilisateur de mettre un appel en attente. Lorsqu’un appel est paré, le service génère un code unique pour l’extraction des appels. L’utilisateur qui a parké l’appel ou quelqu’un d’autre peut ensuite utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel. (Pour plus [d’informations, voir Park a call in Teams.)](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

Voici quelques-uns des scénarios courants d’utilisation du parc d’appels :

- Un appelant appelle une personne travaillant dans une usine. Le réceptioniste annonce ensuite l’appel et le numéro de code sur le système d’adresses public. L’utilisateur pour qui l’appel est en cours peut alors prendre un téléphone Teams aux ateliers et entrer le code pour récupérer l’appel.
- Un utilisateur relaient un appel sur un appareil mobile parce que la batterie de l’appareil est à court de courant. L’utilisateur peut ensuite entrer le code pour récupérer l’appel à partir Teams téléphone de bureau.
- Un représentant du support technique appelle un client et envoie une annonce sur un canal Teams un expert pour récupérer l’appel et aider le client. Un expert entre le code dans Teams clients pour récupérer l’appel

Pour parer et récupérer des appels, un utilisateur doit être un Voix Entreprise et doit être inclus dans une stratégie de parc d’appels.

> [!NOTE]
> Le parcage et la récupération d’appels sont disponibles uniquement [dans Teams mode](teams-and-skypeforbusiness-coexistence-and-interoperability.md) déploiement uniquement et ne sont pas pris en charge Skype Entreprise téléphones IP.

## <a name="configure-call-park-and-retrieve"></a>Configurer le parc d’appel et la récupération

Vous devez être un administrateur Teams configuration du parc d’appels et de la récupération. Il est désactivé par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels. Lorsque vous appliquez la même stratégie à un groupe d’utilisateurs, ceux-là peuvent se parer et récupérer des appels entre eux.

La plage de numéros d’appel est prédéfinée de 10 à 99 et ne peut pas être modifiée. Le premier appel paré s’intituera sur un code de pick-up du 10, le code d’appel 11, etc. sera restituer l’appel en place. jusqu’à ce que 99 soit rendu en tant que code de pick-up. Par la suite, les codes d’pick-up restituer à partir de 10 recommencent.  S’il y a plus de 89 appels en cours parés, les codes d’pick-up restituer continueront d’être incrémentés au-delà de 99, de telle telle que le 90e appel par parcé sera rendu 100 pour un code de pick-up, le 91e appel en cours sera rendu avec le code de collecte 101.

Pour activer une stratégie de parc d’appels

1. Dans le panneau de navigation de gauche du Microsoft Teams d’administration, allez à **Stratégies**  >  **de parc d’appel vocal.**
2. Sous **l’onglet Gérer les stratégies,** cliquez sur **Ajouter.**
3. Donnez un nom à la stratégie, puis basculez **l’accès au parc d’appels** **sur On.** (La plage d’appel et le délai d’appel ne peuvent pas être personnalisés.)

    ![Capture d’écran des paramètres de stratégie de parc d’appel.](media/call-park-add-policy.png)

4. Sélectionnez **Enregistrer**.

Vous pouvez modifier la stratégie en la sélectionnant dans la liste et en cliquant sur **Modifier.**

Pour que la stratégie fonctionne, elle doit être attribuée aux utilisateurs. Vous pouvez [affecter la stratégie à des utilisateurs individuellement](assign-policies.md) ou à un groupe.

Pour affecter une stratégie de parc d’appels à un groupe

1. Dans la page **Stratégies de parc** d’appel, sous l’onglet **Affectation** de stratégie de groupe, cliquez sur Ajouter **un groupe.**
2. Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter.**
3. Choisissez un rang comparé aux autres affectations de groupe.
4. Sous **Sélectionner une stratégie,** choisissez la stratégie à qui vous voulez affecter ce groupe.

    ![image stratégies de parc.](media/call-park-assign-policy-to-group.png)

5. Sélectionnez **Appliquer.**

## <a name="related-topics"></a>Sujets associés

[Par parcer un appel dans Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
