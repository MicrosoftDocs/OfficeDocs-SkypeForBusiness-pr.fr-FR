---
title: "Définir les langues du standard automatique pour les conférences Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Découvrez comment sélectionner les langues de surveillance automatique audioconférence pour un numéro d’audioconférence."
ms.openlocfilehash: c352609926a7bc6bf7f72015447ba9f7ae115487
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Définir les langues du standard automatique pour les conférences Audio

La surveillance automatique de conférence Audio de Skype pour les entreprises et les Teams Microsoft peut accueillir des appelants audio dans un certain nombre de langages différents lorsqu’ils joignent une réunion.
  
Choisir une langue principale et jusqu'à quatre langues secondaires. La langue principale que vous définissez sera utilisée tout d’abord, et les langues secondaires seront utilisés par le standard automatique que vous sélectionnez. 
  
> [!NOTE]
>  Vous pouvez configurer les langues numéros nationaux accès audio uniquement.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Définir la conférence langues de surveillance automatique

Vous devez être un [administrateur global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ou un [Skype pour l’administrateur d’entreprise](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **l’audioconférence**, puis cliquez sur **pont de Microsoft**.
    
4. Sélectionnez le numéro de téléphone de conférence audio à partir de la liste et dans le volet Actions, cliquez sur **langues**. 
    
5. Dans la page **définir les langues** , cliquez sur la liste **langue principale** pour afficher la liste complète des langues disponibles. Si vous le souhaitez, cliquez sur chacune des listes de **langues secondaires** pour sélectionner la langue secondaire.
    
    > [!NOTE]
    > La langue principale et les langues secondaires prises en charge sont répertoriées. L’ordre dans lequel vous les sélectionnez dans les listes sera l’ordre des langues présentée aux appelants. 
  
6. Cliquez sur **Enregistrer**.
    
## <a name="want-else-should-i-know"></a>Informations supplémentaires

- Pour afficher la liste des langues prises en charge pour les conférences Audio, consultez [l’audioconférence de langues prises en charge](audio-conferencing-supported-languages.md).
    
- Langues peuvent être définies pour dédiée mais pas pour les numéros de téléphone partagé.
    
- Pour afficher la liste des pays/régions dans lesquels l’audioconférence dans Office 365 à l’aide de Microsoft comme fournisseur est disponible, voir [numéros de téléphone pour les conférences Audio](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell ?

Pour automatiser cette étape, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) et [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Pour plus d’informations, reportez-vous [à l’aide de Windows PowerShell à faire Skype commune pour les tâches de gestion commerciale en ligne](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
