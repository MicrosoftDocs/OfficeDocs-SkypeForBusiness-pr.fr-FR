---
title: Définir les langues du standard automatique d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Cette section explique comment sélectionner les langues du standard automatique d’audioconférence d’un numéro d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: 44861c1dc7c95afe09194c05f357cf371d00ca43
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754012"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Définir les langues du standard automatique d’audioconférence dans Microsoft Teams

Le standard automatique d’audioconférence pour Microsoft Teams peut accueillir les appelants dans différentes langues lorsqu'ils rejoignent une réunion.
  
Sélectionnez la langue principale et jusqu’à quatre langues secondaires. La langue principale que vous définissez sera utilisée en premier, tandis que les langues secondaires seront utilisées par le standard automatique dans l'ordre que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues de numéros de conférence audio de la catégorie dédiée. Les langues du nombre de services d’audioconférence partagés ne peut pas être modifiés.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir des langues standard automatique de la conférence

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. Sélectionnez un numéro de téléphone de conférence audio **Dedidcated** dans la liste, puis en haut de la page, cliquez sur **Modifier**. Il n’est possible de modifier les langues de numéros de conférence audio dédié. L’option **Modifier** ne s’affiche lorsqu’un numéro de conférence audio dédié est sélectionné.

3. Dans le volet de droite, sélectionnez la langue par défaut et les autres langues. 
 
    > [!NOTE]
    > La valeur par défaut et autres langues prises en charge sont répertoriés. L’ordre dans lequel vous sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 

4. Cliquez sur **Enregistrer**.

    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour voir une liste des pays/régions dans lesquels l’audioconférence dans Office 365 utilisant Microsoft en tant que fournisseur est disponible, voir [Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing-in-teams.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

