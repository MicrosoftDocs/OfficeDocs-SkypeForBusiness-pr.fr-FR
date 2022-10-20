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
description: Découvrez comment utiliser le parcage d’appels et récupérer pour mettre un appel en attente dans Microsoft Teams.
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614237"
---
# <a name="configure-call-park-and-retrieve"></a>Configurer le parc d’appels et récupérer

Appeler le parcage et récupérer permet à un utilisateur de mettre un appel en attente. Lorsqu’un appel est garé, le service génère un code unique pour la récupération des appels. L’utilisateur qui a garé l’appel ou une autre personne peut ensuite utiliser ce code avec une application ou un appareil pris en charge pour récupérer l’appel. (Pour plus d’informations, consultez [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).)

Voici quelques-uns des scénarios courants d’utilisation du parc d’appels :

- Une réceptionniste appelle quelqu’un qui travaille dans une usine. Le serveur de réception annonce ensuite l’appel et le numéro de code sur le système d’adressage public. L’utilisateur pour lequel l’appel est destiné peut ensuite récupérer un téléphone Teams à l’étage de l’usine et entrer le code pour récupérer l’appel.

- Un utilisateur parcs un appel sur un appareil mobile parce que la batterie de l’appareil est à court d’alimentation. L’utilisateur peut ensuite entrer le code pour récupérer l’appel à partir d’un téléphone de bureau Teams.

- Un représentant du support technique parcs un appel client et envoie une annonce sur un canal Teams pour qu’un expert récupère l’appel et aide le client. Un expert entre le code dans les clients Teams pour récupérer l’appel.

Pour garer et récupérer des appels, un utilisateur doit être un utilisateur Téléphonie –  Grandes entreprises et doit être inclus dans une stratégie de parc d’appels.

Par défaut, la plage de numéros de prise d’appel est comprise entre 10 et 99. Vous pouvez également créer votre propre plage personnalisée comprise entre 10 et 9999. Le premier appel parqué affiche un code de prise du début de la plage (par exemple, 10). Le prochain appel parqué sera rendu par un code de prise incrémenté de 1 ; c’est-à-dire, 11, et ainsi de suite, jusqu’à ce que la fin de la plage soit restitagée en tant que code de prise. Après quoi, les codes de prise rendus redémarrent à partir du début de la plage. 

Vous pouvez spécifier un délai d’expiration comme nombre de secondes d’attente avant de sonner en arrière lorsque l’appel parqué n’a pas été récupéré. La plage autorisée est comprise entre 120 et 1800 secondes, et la valeur par défaut est 300 secondes.

Pour configurer le parc d’appels et récupérer, vous devez être administrateur Teams. Elle est désactivée par défaut. Vous pouvez l’activer pour les utilisateurs et créer des groupes d’utilisateurs à l’aide de la stratégie de parc d’appels. Lorsque vous appliquez la même stratégie à un ensemble d’utilisateurs, ils peuvent stationner et récupérer des appels entre eux.

> [!NOTE]
> Le parc d’appels et la récupération sont uniquement disponibles en [mode de déploiement Teams uniquement](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Il n’est pas pris en charge sur Skype Entreprise téléphones IP.

Vous pouvez configurer le parcage d’appels et le récupérer à l’aide du Centre d’administration Teams ou de PowerShell.

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

Pour créer une instance de stratégie de parc d’appels :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **stratégies de parc d’appels** **vocaux** > .

2. Sous l’onglet **Gérer les stratégies** , cliquez sur **Ajouter**.

3. Donnez un nom à la stratégie, puis **basculez Autoriser le parc d’appels** sur **Activé**.

4. Modifiez la plage et le délai d’expiration du parc selon les besoins.

5. Sélectionnez **Enregistrer**.

Vous pouvez modifier la stratégie en la sélectionnant dans la liste et en cliquant sur **Modifier**.

Pour que la stratégie fonctionne, elle doit être affectée aux utilisateurs. Vous pouvez [affecter la stratégie aux utilisateurs individuellement](assign-policies-users-and-groups.md) ou les affecter à un groupe.

Pour affecter une stratégie de parc d’appels à un groupe :

1. Dans la page **Stratégies de parc d’appels** , sous l’onglet **Affectation de stratégie** de groupe, cliquez sur Ajouter un **groupe**.

2. Recherchez le groupe que vous souhaitez utiliser, puis cliquez sur **Ajouter**.

3. Choisissez un classement par rapport à d’autres affectations de groupe.

4. Sous **Sélectionner une stratégie**, choisissez la stratégie à laquelle vous souhaitez affecter ce groupe.

5. Sélectionnez **Appliquer**.

## <a name="use-powershell"></a>Utiliser PowerShell

Pour gérer le parcage d’appels et récupérer des stratégies à l’aide de PowerShell, utilisez les applets de commande du module Teams PowerShell suivantes :

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>Exemples

#### <a name="new-custom-call-park-policy"></a>Nouvelle stratégie de parc d’appels personnalisé

L’exemple suivant crée une stratégie de parc d’appels personnalisée qui génère des numéros de prise de 500 à 1500, et qui rappelle le parker après 600 secondes si l’appel parqué est sans réponse.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>Modifier une stratégie de parc d’appels

L’exemple suivant désactive la stratégie de parc d’appels :

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>Accorder une stratégie de parc d’appels à un utilisateur

L’exemple suivant accorde la stratégie de parc d’appels à un utilisateur :

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>Supprimer une stratégie de parc d’appels

L’exemple suivant supprime la stratégie de parc d’appels :

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>Rubriques connexes

[Parcer un appel dans Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

