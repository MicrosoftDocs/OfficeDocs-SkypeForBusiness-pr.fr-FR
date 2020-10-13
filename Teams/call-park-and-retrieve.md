---
title: Parcage et récupération d’appel dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: En savoir plus sur l’utilisation du parc d’appels et la récupération pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424592"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcage et récupération d’appel dans Microsoft Teams

Le parc et la récupération des appels est une fonctionnalité qui permet à un utilisateur de mettre un appel en attente. Lorsqu’un appel est parqué, le service génère un code unique pour la récupération des appels. L’utilisateur qui a parqué l’appel ou quelqu’un d’autre peut alors utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel. (Pour plus d’informations, consultez la section voir [Park a Call in teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) .)

Voici quelques-uns des scénarios les plus courants d’utilisation du parc d’appel :

- Un réceptionniste est un appel pour une personne qui travaille dans une fabrique. La réceptionniste annonce ensuite l’appel et le numéro de code sur le système d’adresses publiques. L’utilisateur pour lequel l’appel est destiné peut alors décrocher un téléphone d’équipe sur le plancher et entrer le code permettant de récupérer l’appel.
- Un utilisateur a un appel sur un appareil mobile, car la batterie de l’appareil est épuisée. L’utilisateur peut ensuite entrer le code permettant de récupérer l’appel à partir d’un téléphone de bureau Teams.
- Un représentant du support technique Centre un appel client et envoie une annonce à un canal d’équipe pour permettre à un expert de récupérer l’appel et d’aider le client. Un expert entre le code dans les clients teams pour récupérer l’appel

Pour le stationnement et la récupération des appels, l’utilisateur doit être un utilisateur de voix entreprise et doit être inclus dans une stratégie de parc d’appels.

> [!NOTE]
> Le parc et la récupération d’appels ne sont disponibles qu’en [mode de déploiement d’équipes](teams-and-skypeforbusiness-coexistence-and-interoperability.md) et ne sont pas pris en charge sur les téléphones IP Skype entreprise.

## <a name="configure-call-park-and-retrieve"></a>Configurer le parc d’appels et la récupération

Vous devez être administrateur d’équipes pour configurer le parc d’appels et la récupération. Elle est désactivée par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels. Lorsque vous appliquez la même politique à un ensemble d’utilisateurs, ces derniers peuvent se parcer et récupérer les appels entre eux.

Pour activer une stratégie de parc d’appels

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies de parc d’appels**vocaux.
2. Sous l’onglet **gérer les stratégies** , cliquez sur **Ajouter**.
3. Attribuez un nom à la stratégie, puis basculez **autoriser le parc d’appels** sur **activé**.

    ![Capture d’écran des paramètres de stratégie de parc d’appels](media/call-park-add-policy.png)

4. Sélectionnez **Save (enregistrer**).

Vous pouvez modifier la stratégie en la sélectionnant dans la liste, puis en cliquant sur **modifier**.

Pour que la stratégie puisse fonctionner, elle doit être attribuée à des utilisateurs. Vous pouvez [affecter la stratégie aux utilisateurs individuellement](assign-policies.md) ou les affecter à un groupe.

Pour attribuer une stratégie de composant d’appel à un groupe

1. Dans la page **stratégies de parc d’appels** , sous l’onglet affectation de stratégie de **Groupe** , cliquez sur Ajouter un **groupe**.
2. Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter**.
3. Choisissez un classement par rapport aux autres affectations de groupe.
4. Sous **Sélectionner une stratégie**, sélectionnez la stratégie que vous souhaitez attribuer à ce groupe.

    ![](media/call-park-assign-policy-to-group.png)

5. Cliquez sur **Appliquer**.

## <a name="related-topics"></a>Rubriques connexes

[Park a Call en teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)

[Nouveau-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)