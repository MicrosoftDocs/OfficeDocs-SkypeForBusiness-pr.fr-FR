---
title: Définir la longueur du code confidentiel pour les réunions d'audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Découvrez les paramètres définissant la longueur et les exigences d’un code confidentiel et comment définir sa longueur pour les réunions dans Microsoft Teams.
ms.openlocfilehash: db7c62920dc7440cc8356dd3f5275dd551cdfd78
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014916"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Définir la longueur du code confidentiel pour les réunions d'audioconférence dans Microsoft Teams

Lorsque vous configurez des services d’audioconférence Teams Microsoft, vous obtiendrez un pont de conférence audio. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous avez figureront dans les invitations de réunion pour l’application Microsoft Teams.
  
Le pont de conférence audio répond à un appel pour les personnes qui sont connectent à une réunion à l’aide d’un téléphone. Il répond à l’appelant à invites vocales à partir d’un standard automatique, puis, en fonction de vos paramètres, peut lire des notifications et poser aux appelants à enregistrer leur nom. Les **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et l’expérience d’accès aux réunions, et de définir la longueur des codes confidentiels utilisés par les organisateurs de réunions. Organisateurs de réunion permet de démarrer les réunions si elles ne peuvent pas participer à la réunion à l’aide de l’application Microsoft Teams codes confidentiels.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Définir la longueur du code confidentiel

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), sous **Longueur du code confidentiel**, sélectionnez le nombre de chiffres que vous voulez pour le code confidentiel.

4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion. 

## <a name="want-to-know-more-about-pin-settings"></a>Vous souhaitez en savoir plus sur les paramètres des codes confidentiels ?

- Codes confidentiels peuvent être de 4 à 12 chiffres ; la valeur par défaut est 5. Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels. Les lettres et les caractères spéciaux ne sont pas autorisés.
    
- Un code confidentiel est uniquement requis pour l’organisateur de la réunion lorsqu’un utilisateur Teams Microsoft n’a pas déjà démarré la réunion. Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.
    
- Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
