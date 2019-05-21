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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Découvrez comment sélectionner les langues du standard automatique d’audioconférence pour un numéro d’audioconférence dans Skype Entreprise Online.
ms.openlocfilehash: a05b393ac671447c0efe385bb1d562039aef32d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306377"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Définir les langues du standard automatique pour l’Audioconférence dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur la définition de la langue de standard automatique dans Microsoft Teams, veuillez consulter[Définir les langues de standard automatique pour l’audioconférence dans Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Le standard automatique d’audioconférence pour Skype Entreprise permet d’accueillir les appelants dans un certain nombre de langues différentes lorsqu’ils rejoignent une réunion.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Vous pouvez uniquement modifier les langues des numéros de conférence audio qui appartiennent à la catégorie dédiée. Les langues du numéro de conférence audio partagé ne peuvent pas être modifiées.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir les langues du standard automatique des conférences

Vous devez être un [administrateur global d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou un [administrateur Skype Entreprise](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
    
1. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, accédez à l' **ancien portail**. Dans le portail hérité, sélectionnez **audioconférence**, puis cliquez sur **pont Microsoft**.
    
2. Sélectionnez le numéro de téléphone de l’audioconférence dans la liste, puis, dans le volet action, cliquez sur **définir les langues**. Il est uniquement possible de modifier les langues des numéros de conférence audio dédiés.  
    
3. Dans la page **définir les langues** , cliquez sur la liste de langues **principales** pour afficher la liste complète des langues disponibles. Le cas échéant, cliquez sur l’une des listes de **langues secondaires** pour sélectionner langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous les sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 
  
4. Cliquez sur **Enregistrer**.
    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge par l’audioconférence, consultez [Langues prises en charge par l’audioconférence](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Des langues peuvent être définies pour des numéros dédiés, mais pas pour des numéros de téléphone partagés.
    
- Pour voir une liste des pays/régions dans lesquels l’audioconférence dans Office 365 utilisant Microsoft en tant que fournisseur est disponible, voir [Numéros de téléphone pour l’audioconférence](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les applets de action [Set-csonlinedialinconferencingservicenumberhttp](https://go.microsoft.com/fwlink/?LinkId=617689) et [get-//go.Microsoft.com/fwlink/](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Pour plus d’informations, reportez-vous à la rubrique [utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038) .
  
## <a name="related-topics"></a>Voir aussi

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
