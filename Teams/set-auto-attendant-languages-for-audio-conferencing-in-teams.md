---
title: Définir les langues du standard automatique pour les conférences audio
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Cette section explique comment sélectionner les langues du standard automatique d’audioconférence d’un numéro d’audioconférence dans Microsoft Teams.
ms.openlocfilehash: d7f6893bfc9c58131fe596597afc1ac90389d908
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691130"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Définir les langues du standard automatique d’audioconférence dans Microsoft Teams

Le standard automatique d’audioconférence pour Microsoft Teams peut accueillir les appelants dans différentes langues lorsqu'ils rejoignent une réunion.
  
Sélectionnez la langue principale et jusqu’à quatre langues secondaires. La langue principale que vous définissez sera utilisée en premier, tandis que les langues secondaires seront utilisées par le standard automatique dans l'ordre que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues des numéros de conférence audio qui appartiennent à la catégorie dédiée. Les langues du numéro de conférence audio partagé ne peuvent pas être modifiées.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir les langues du standard automatique des conférences

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. Sélectionnez un numéro de téléphone **dédié** à la conférence audio dans la liste, puis cliquez sur **modifier**en haut de la page. Il est uniquement possible de modifier les langues des numéros de conférence audio dédiés. L’option **modifier** ne s’affiche qu’en cas de sélection d’un numéro de conférence audio dédié.

3. Dans le volet de droite, choisissez la langue par défaut que vous voulez utiliser, ainsi que d’autres langues. 
 
    > [!NOTE]
    > Les langues par défaut et de remplacement prises en charge sont indiquées. L’ordre dans lequel vous les sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 

4. Cliquez sur **Enregistrer**.

    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour afficher une liste des pays/régions dans lesquels une audioconférence est disponible dans Microsoft 365 ou Office 365 en utilisant Microsoft comme fournisseur, voir [numéros de téléphone pour les conférences audio](phone-numbers-for-audio-conferencing-in-teams.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour plus d’informations, consultez la [référence Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
  
## <a name="related-topics"></a>Rubriques connexes

[Essayez ou achetez une audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

