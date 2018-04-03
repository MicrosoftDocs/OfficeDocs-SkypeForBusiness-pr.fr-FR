---
title: Définir la longueur du code confidentiel pour les réunions de la conférence de l’Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 442ec6f4395b71acaf3296bdd6ec6317451dc36f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Définir la longueur du code confidentiel pour les réunions de la conférence de l’Audio

Lorsque vous configurez une conférence audio dans pour Skype pour entreprise ou Teams de Microsoft, vous obtiendrez un pont de téléconférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous avez figurera sur les invitations réunion pour Skype pour les applications d’entreprise et Teams de Microsoft.
  
Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone. Elle répond à l’appelant avec des invites vocales d’une surveillance automatique, puis, en fonction de vos paramètres, peut lire les notifications et demandez aux appelants d’enregistrer leur nom. **Paramètres du pont Microsoft** vous autorise à modifier les paramètres pour les notifications de réunion et la réunion de joindre l’expérience et de définir la longueur des broches qui sont utilisés par les organisateurs de la réunion. Les organisateurs de la réunion utilisent broches pour démarrer les réunions si elles ne peuvent pas joindre la réunion à l’aide de la Skype pour application métier ou Teams de Microsoft.
  
## <a name="setting-the-pin-length"></a>Définir la longueur du code confidentiel

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Sous **sécurité** > **longueur de broche**, sélectionnez le nombre de chiffres que vous souhaitez pour le code confidentiel, puis cliquez sur **Enregistrer**.
    
> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Vous souhaitez en savoir plus sur les paramètres de code PIN ?

- Codes personnels peut être de 4 à 12 chiffres ; la valeur par défaut est 5. Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels. Les lettres et les caractères spéciaux ne sont pas autorisés.
    
- Un code PIN n’est requis pour la réunion lorsqu’un Skype pour l’utilisateur professionnel ou Teams de Microsoft n’a pas déjà commencée. Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.
    
- Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).
    
- Pour définir le nombre de chiffres du code confidentiel sur 8 :  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Voir aussi

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
