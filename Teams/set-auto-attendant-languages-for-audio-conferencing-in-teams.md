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
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Cette section explique comment sélectionner les langues du standard automatique d’audioconférence d’un numéro d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: e99892ad42a8e7340558b8f0db7daa1da025777a
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344249"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Définir les langues du standard automatique d’audioconférence dans Microsoft Teams

Le standard automatique d’audioconférence pour Microsoft Teams peut accueillir les appelants dans différentes langues lorsqu'ils rejoignent une réunion.
  
Sélectionnez la langue principale et jusqu’à quatre langues secondaires. La langue principale que vous définissez sera utilisée en premier, tandis que les langues secondaires seront utilisées par le standard automatique dans l'ordre que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues des numéros de conférence audio qui appartiennent à la catégorie dédiée. Les langues du numéro de conférence audio partagé ne peuvent pas être modifiées.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir les langues du standard automatique des conférences

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. Sélectionnez un numéro de téléphone **dédié** à la conférence audio dans la liste, puis cliquez sur **modifier**en haut de la page. Il est uniquement possible de modifier les langues des numéros de conférence audio dédiés. L’option **modifier** ne s’affiche qu’en cas de sélection d’un numéro de conférence audio dédié.

3. Dans le volet de droite, choisissez la langue par défaut que vous voulez utiliser, ainsi que d’autres langues. 
 
    > [!NOTE]
    > Les langues par défaut et de remplacement prises en charge sont indiquées. L’ordre dans lequel vous les sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 

4. Cliquez sur **Enregistrer**.

    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour voir une liste des pays/régions dans lesquels l’audioconférence dans Office 365 utilisant Microsoft en tant que fournisseur est disponible, voir [Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing-in-teams.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour plus d’informations, consultez la [référence Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
  
## <a name="related-topics"></a>Voir aussi

[Tester ou acheter l’audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

