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
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163900"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Définir les langues du standard automatique pour l’Audioconférence dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur la définition de la langue de standard automatique dans Microsoft Teams, veuillez consulter[Définir les langues de standard automatique pour l’audioconférence dans Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Le standard automatique d’audioconférence pour Skype Entreprise permet d’accueillir les appelants dans un certain nombre de langues différentes lorsqu’ils rejoignent une réunion.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues des numéros d’audioconférence de la catégorie Dédié. Les langues du numéro d’audioconférence partagée ne peuvent pas être modifiées.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir les langues du attendant automatique de conférence

Vous devez être un [administrateur global ou](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) un administrateur de [Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Entreprise pour effectuer cette étape.
    
1. Dans le **Centre d’administration Skype Entreprise,** dans le panneau de navigation de gauche, allez sur **le portail hérité.** Une fois dans l’ancien portail, sélectionnez **Audioconférence,** puis cliquez sur **Pont Microsoft.**
    
2. Sélectionnez le numéro de téléphone de l’audioconférence dans la liste, puis dans le volet Action, cliquez **sur Définir les langues.** Il est uniquement possible de modifier les langues des numéros d’audioconférence dédiés.  
    
3. Dans la page **Définir les langues,** cliquez **sur** la liste Langue principale pour afficher la liste complète des langues disponibles. Si nécessaire, cliquez sur chacune des listes de **langues secondaires** pour sélectionner la langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous les sélectionnez dans les listes est l’ordre des langues présentées aux appelants. 
  
4. Cliquez sur **Enregistrer**.
    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour obtenir la liste des pays et régions dans lesquels l’audioconférence est disponible dans Microsoft 365 ou Office 365 en utilisant Microsoft comme fournisseur, consultez les numéros de téléphone pour [audioconférence.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les [cmdlets Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) et [Get-CsOnlineDialInConferencingLanguagesSupported.](https://go.microsoft.com/fwlink/?LinkId=617684)
  
Pour en savoir plus, [consultez Utiliser Windows PowerShell pour effectuer les tâches courantes de gestion de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Sujets associés

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
