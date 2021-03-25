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
description: Découvrez comment utiliser le parc d’appels et récupérer pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: 11c0abc5c9cd49a524417ce9706129cea9ccae1e
ms.sourcegitcommit: 84d99b266dea2a972774d781b92eccc67d6c197a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197579"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Parcage et récupération d’appel dans Microsoft Teams

La fonctionnalité Parcer et récupérer des appels permet à un utilisateur de mettre un appel en attente. Lorsqu’un appel est paré, le service génère un code unique pour l’extraction des appels. L’utilisateur qui a parké l’appel ou quelqu’un d’autre peut ensuite utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel. (Pour plus [d’informations, voir Parcer](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) un appel dans Teams.)

Voici quelques-uns des scénarios courants d’utilisation du parc d’appels :

- Un appelant appelle une personne travaillant dans une usine. Le réceptioniste annonce ensuite l’appel et le numéro de code sur le système d’adresses public. L’utilisateur pour qui l’appel est en cours peut alors prendre un téléphone Teams aux 400 premières lignes et entrer le code pour récupérer l’appel.
- Un utilisateur relaient un appel sur un appareil mobile parce que la batterie de l’appareil est à court de courant. L’utilisateur peut ensuite entrer le code pour récupérer l’appel à partir d’un téléphone de bureau Teams.
- Un représentant du support technique appelle un client et envoie une annonce sur un canal Teams pour qu’un expert récupère l’appel et aide le client. Un expert entre le code dans les clients Teams pour récupérer l’appel

Pour parer et récupérer des appels, un utilisateur doit être un Voix Entreprise et être inclus dans une stratégie de parc d’appels.

> [!NOTE]
> Le parcage et la récupération d’appels sont uniquement disponibles en mode de [déploiement de Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) uniquement et ne sont pas pris en charge sur les téléphones IP Skype Entreprise.

## <a name="configure-call-park-and-retrieve"></a>Configurer le parc d’appel et la récupération

Vous devez être un administrateur Teams pour configurer le parc d’appels et la récupération. Il est désactivé par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels. Lorsque vous appliquez la même stratégie à un groupe d’utilisateurs, ceux-là peuvent se parer et récupérer les appels entre eux.

Pour activer une stratégie de parc d’appels

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez **aux** stratégies  >  **de parcation de l’appel vocal.**
2. Sous **l’onglet Gérer les stratégies,** cliquez sur **Ajouter.**
3. Donnez un nom à la stratégie, puis basculez **l’accès au parc d’appels** **sur On.**

    ![Capture d’écran des paramètres de stratégie de parc d’appel](media/call-park-add-policy.png)

4. Sélectionnez **Enregistrer**.

Vous pouvez modifier la stratégie en la sélectionnant dans la liste, puis en cliquant sur **Modifier.**

Pour que la stratégie fonctionne, elle doit être affectée aux utilisateurs. Vous pouvez [affecter la stratégie à des utilisateurs individuellement](assign-policies.md) ou à un groupe.

Pour affecter une stratégie de parc d’appel à un groupe

1. Dans la page **Stratégies de parc** d’appel, sous l’onglet **Affectation** de stratégie de groupe, cliquez sur Ajouter **un groupe.**
2. Recherchez le groupe que vous voulez utiliser, puis cliquez sur **Ajouter.**
3. Choisissez un rang comparé aux autres affectations de groupe.
4. Sous **Sélectionner une stratégie,** choisissez la stratégie à qui vous voulez affecter ce groupe.

    ![Image stratégies de parc](media/call-park-assign-policy-to-group.png)

5. Sélectionnez **Appliquer.**

## <a name="related-topics"></a>Voir aussi

[Pare-tête dans Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Attribuer des stratégies à vos utilisateurs](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)