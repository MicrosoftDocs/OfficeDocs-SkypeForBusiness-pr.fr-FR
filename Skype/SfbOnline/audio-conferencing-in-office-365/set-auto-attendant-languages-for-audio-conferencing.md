---
title: Définir les langues du standard automatique pour les conférences Audio
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Voir comment sélectionner les langues standard automatique de conférence audio pour un nombre de services d’audioconférence.
ms.openlocfilehash: c4461f61ce05afedc2663a3e5b61d37370394cd4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Définir les langues du standard automatique pour les conférences Audio

Le standard automatique de conférence Audio pour Skype pour les entreprises et Teams Microsoft peut accueillir les appelants audio dans un certain nombre de différentes langues lorsqu’ils rejoignent une réunion.
  
Choisissez une langue principale et jusqu'à quatre langues secondaires. La langue principale que vous avez définie est utilisée en premier et les langues secondaires seront utilisés par le standard automatique que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez configurer les langues sur les numéros d’accès audio interne uniquement.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir des langues standard automatique de la conférence

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**.

2. Sélectionnez le numéro de téléphone de conférence audio à partir de la liste, puis en haut de la page, cliquez sur **Modifier**.

3. Dans le volet de droite, sélectionnez la langue par défaut et les autres langues. 
 
    > [!NOTE]
    > La valeur par défaut et autres langues prises en charge sont répertoriés. L’ordre dans lequel vous sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 

4. Cliquez sur **Appliquer**.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de Skype pour les entreprises en ligne**

Vous devez être un [administrateur global d’Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou un [Skype pour administrateur d’entreprise](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.
    
2. Sélectionnez le numéro de téléphone de conférence audio à partir de la liste et dans le volet Actions, cliquez sur **langues**. 
    
3. Dans la page **définir les langues** , cliquez sur la liste **langue principale** pour afficher la liste complète des langues disponibles. Si vous avez besoin, cliquez sur chacun des listes de **langues secondaires** pour sélectionner la langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous sélectionnez dans les listes sera l’ordre des langues présentées aux appelants. 
  
4. Cliquez sur **Enregistrer**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour voir la liste des langues prises en charge pour une audioconférence, consultez [audioconférence langues prises en charge](audio-conferencing-supported-languages.md).
    
- Langues peuvent être définies pour dédiée, mais pas pour les numéros de téléphone partagé.
    
- Pour voir une liste de pays/régions dans lesquels la conférence dans Office 365 à l’aide de Microsoft en tant que le fournisseur est disponible, voir [les numéros de téléphone pour une audioconférence](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) et [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Pour plus d’informations, voir [L’aide de Windows PowerShell faire Skype courantes pour les tâches de gestion en ligne Business](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
