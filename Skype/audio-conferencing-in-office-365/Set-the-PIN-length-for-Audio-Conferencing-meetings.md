---
title: "Définir la longueur du code confidentiel pour les réunions de la conférence de l’Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Découvrez les paramètres de la longueur et les exigences de code PIN et la définition de la longueur pour les réunions dans Skype pour les entreprises."
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Définir la longueur du code confidentiel pour les réunions de la conférence de l’Audio

Lorsque vous configurez une conférence audio dans pour Skype pour entreprise ou Teams de Microsoft, vous obtiendrez un pont de téléconférence audio. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous avez figurera sur les invitations réunion pour Skype pour les applications d’entreprise et Teams de Microsoft.
  
Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone. Elle répond à l’appelant avec des invites vocales d’une surveillance automatique, puis, en fonction de vos paramètres, peut lire les notifications et demandez aux appelants d’enregistrer leur nom. **Paramètres du pont Microsoft** vous autorise à modifier les paramètres pour les notifications de réunion et la réunion de joindre l’expérience et de définir la longueur des broches qui sont utilisés par les organisateurs de la réunion. Les organisateurs de la réunion utilisent broches pour démarrer les réunions si elles ne peuvent pas joindre la réunion à l’aide de la Skype pour application métier ou Teams de Microsoft.
  
## <a name="setting-the-pin-length"></a>Définition de la longueur du code confidentiel

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Sous **sécurité** > **longueur de broche**, sélectionnez le nombre de chiffres que vous souhaitez pour le code confidentiel, puis cliquez sur **Enregistrer**.
    
> [!NOTE]
> Un code PIN est différent d’un ID de conférence. ID de conférence sont utilisées par les appelants lorsqu’ils joignent la réunion. Ils sont utilisés pour identifier la réunion. Le code PIN est utilisé pour authentifier l’appelant en tant qu’organisateur de la réunion. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Vous souhaitez en savoir plus sur les paramètres de code PIN ?

- Codes personnels peut être de 4 à 12 chiffres ; la valeur par défaut est 5. Les numéros ne sont utilisés que lors de la création des broches. Lettres et caractères spéciaux ne sont pas utilisés.
    
- Un code PIN n’est requis pour la réunion lorsqu’un Skype pour l’utilisateur professionnel ou Teams de Microsoft n’a pas déjà commencée. Si tout le monde appelle à la réunion, le code confidentiel est requis pour l’organisateur de la réunion démarrer la réunion.
    
- Paramètres de sécurité de code PIN sont appliquées à tous les numéros de téléphone qui sont associés à un pont de Microsoft. Ils seront appliqueront à toutes les réunions qui utilisent les numéros de téléphone associés à un pont donné. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou d’automatiser cette action, vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Pour définir le nombre de chiffres dans le code confidentiel à 8 :`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell est la gestion des utilisateurs et les utilisateurs qui sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 à l’aide d’un unique point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Utiliser Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Voir aussi

[Configurer l’audioconférence pour Skype Entreprise et Microsoft Teams](set-up-audio-conferencing.md)

