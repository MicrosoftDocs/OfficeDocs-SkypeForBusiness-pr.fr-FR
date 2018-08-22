---
title: Définir les langues de standard automatique pour une audioconférence dans Skype pour Business en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Voir comment sélectionner les langues standard automatique de conférence audio pour un nombre de services d’audioconférence dans Skype pour Business Online.
ms.openlocfilehash: 026a09290c6e008493784c0d883220e03d13559f
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490514"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Définir les langues de standard automatique pour une audioconférence dans Skype pour Business en ligne

> [!Note]
> Pour plus d’informations sur la définition de la langue de standard automatique dans Microsoft Teams, voir [définir les langues de standard automatique pour une audioconférence dans les équipes Microsoft](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Le standard automatique de conférence Audio pour Skype pour les entreprises permettre accueillir les appelants audio dans un certain nombre de différentes langues lorsqu’ils rejoignent une réunion.
  
Choisissez une langue principale et jusqu'à quatre langues secondaires. La langue principale que vous avez définie est utilisée en premier et les langues secondaires seront utilisés par le standard automatique que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez configurer les langues sur les numéros d’accès audio interne uniquement.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir des langues standard automatique de la conférence

Vous devez être un [administrateur global d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou un [Skype pour administrateur d’entreprise](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.
    
2. Sélectionnez le numéro de téléphone de conférence audio à partir de la liste et dans le volet Actions, cliquez sur **langues**. 
    
3. Dans la page **définir les langues** , cliquez sur la liste **langue principale** pour afficher la liste complète des langues disponibles. Si vous avez besoin, cliquez sur chacun des listes de **langues secondaires** pour sélectionner la langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 
  
4. Cliquez sur **Enregistrer**.
    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge pour une audioconférence, consultez [audioconférence langues prises en charge](audio-conferencing-supported-languages.md).
    
- Langues peuvent être définies pour dédiée, mais pas pour les numéros de téléphone partagé.
    
- Pour voir une liste de pays/régions dans lesquels la conférence dans Office 365 à l’aide de Microsoft en tant que le fournisseur est disponible, voir [les numéros de téléphone pour une audioconférence](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) et [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Pour plus d’informations, voir [L’aide de Windows PowerShell faire Skype courantes pour les tâches de gestion en ligne Business](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
