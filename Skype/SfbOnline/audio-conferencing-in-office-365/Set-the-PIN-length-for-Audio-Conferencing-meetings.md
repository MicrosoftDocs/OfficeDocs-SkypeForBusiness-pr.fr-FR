---
title: Définir la longueur du code confidentiel pour les réunions de conférence Audio dans Skype pour Business en ligne
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 54ee8e70972a7033a9a759f8df37647ba5a2b700
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490564"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Définir la longueur du code confidentiel pour les réunions de conférence Audio dans Skype pour Business en ligne


> [!NOTE]
> Pour plus d’informations sur la définition de la longueur du code confidentiel dans Microsoft Teams, voir [définir la longueur du code confidentiel pour les réunions de conférence Audio dans les équipes Microsoft](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).

Lorsque vous configurez des services d’audioconférence Skype pour les entreprises, vous obtiendrez un pont de conférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous avez figureront dans les invitations de réunion pour le Skype pour l’application de gestion.
  
Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone. Il répond à l’appelant à invites vocales à partir d’un standard automatique, puis, en fonction de vos paramètres, peut lire des notifications et poser aux appelants à enregistrer leur nom. **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et la réunion expérience de participation aux et définir la longueur des codes confidentiels qui sont utilisés par les organisateurs de réunion. Organisateurs de réunion permet de démarrer les réunions si elles ne peuvent pas participer à la réunion à l’aide de la Skype pour l’application de gestion des codes confidentiels.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Définir la longueur du code confidentiel
 
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
2. Sous **sécurité** > **longueur du code confidentiel**, sélectionnez le nombre de chiffres pour le code confidentiel, puis cliquez sur **Enregistrer**.
    
> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion. 

## <a name="want-to-know-more-about-pin-settings"></a>Vous souhaitez en savoir plus sur les paramètres de code confidentiel ?

- Codes confidentiels peuvent être de 4 à 12 chiffres ; la valeur par défaut est 5. Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels. Les lettres et les caractères spéciaux ne sont pas autorisés.
    
- Un code confidentiel est uniquement requis pour l’organisateur lorsqu’une Skype pour l’utilisateur d’entreprise n’a pas déjà démarré la réunion. Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.
    
- Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser la procédure, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757).
    
- Pour définir le nombre de chiffres du code confidentiel sur 8 :  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Voir aussi

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
