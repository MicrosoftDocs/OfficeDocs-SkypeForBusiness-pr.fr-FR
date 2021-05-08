---
title: Définir les langues du standard automatique pour l’Audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Découvrez comment sélectionner les langues du standard automatique d’audioconférence pour un numéro d’audioconférence dans Skype Entreprise Online.
ms.openlocfilehash: 714312989bc3898fea2ed0d335fed8f5f2eebbb3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237020"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Définir les langues du standard automatique pour l’Audioconférence dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Pour plus d’informations sur la définition de la langue de standard automatique dans Microsoft Teams, veuillez consulter[Définir les langues de standard automatique pour l’audioconférence dans Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Le standard automatique d’audioconférence pour Skype Entreprise permet d’accueillir les appelants dans un certain nombre de langues différentes lorsqu’ils rejoignent une réunion.
  
Choisir une langue principale et jusqu’à quatre langues secondaires. La langue principale que vous définissez est utilisée en premier et les langues secondaires sont utilisées par le attendant automatique dans l’ordre dans l’ordre dans celui-ci. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues des numéros d’audioconférence de la catégorie Dédié. Les langues du numéro d’audioconférence partagée ne peuvent pas être modifiées.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir les langues du attendant automatique de conférence

Vous devez être un [administrateur global ou un](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Skype Entreprise [administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
    
1. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez sur **portail hérité.** Une fois dans l’ancien portail, sélectionnez **Audioconférence,** puis cliquez sur **Pont Microsoft.**
    
2. Sélectionnez le numéro de téléphone de l’audioconférence dans la liste, puis dans le volet Action, cliquez **sur Définir les langues.** Il est uniquement possible de modifier les langues des numéros d’audioconférence dédiés.  
    
3. Dans la page **Définir les langues,** cliquez **sur** la liste Langue principale pour afficher la liste complète des langues disponibles. Si nécessaire, cliquez sur chacune des listes de **langues secondaires** pour sélectionner la langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous les sélectionnez dans les listes est l’ordre des langues présentées aux appelants. 
  
4. Cliquez sur **Enregistrer**.
    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour obtenir la liste des pays et régions dans lesquels l’audioconférence dans Microsoft 365 ou Office 365 en utilisant Microsoft comme fournisseur est disponible, consultez les numéros Téléphone pour [l’audioconférence.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les cmdlets [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) et [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)
  
Pour plus d’informations, voir Utiliser Windows PowerShell pour effectuer les tâches courantes [de gestion Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Rubriques connexes

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
