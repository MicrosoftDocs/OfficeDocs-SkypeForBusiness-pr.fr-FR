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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Découvrez les paramètres de longueur et les exigences d’un code confidentiel et apprenez à définir la durée des réunions dans Microsoft Teams.
ms.openlocfilehash: 7f7f477d14556baa7d2a47e5062aacd5de5796fd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693999"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Définir la longueur du code confidentiel pour les réunions d'audioconférence dans Microsoft Teams

Lorsque vous configurez l’audioconférence pour Microsoft Teams, vous obtenez un pont d’audioconférence. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous définissez sera inclus dans les invitations à participer à la réunion de l’application Microsoft Teams.
  
Le pont d’audioconférence répond à l’appel des personnes qui composent un numéro pour accéder à une réunion en utilisant un téléphone. Il répond à l’appelant avec des invites vocales d’un standard automatique de conférence puis, en fonction de vos paramètres, il peut lire des notifications et demander aux appelants d’enregistrer leur nom. Les **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et l’expérience d’accès aux réunions, et de définir la longueur des codes confidentiels utilisés par les organisateurs de réunions. Les organisateurs de réunions utilisent des codes confidentiels s'ils ne peuvent pas rejoindre la réunion en utilisant l’application Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Définir la longueur du code confidentiel

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **paramètres du pont** , sous longueur du **code confidentiel**, sélectionnez le nombre de chiffres que vous voulez utiliser pour le code confidentiel.

4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion. 

## <a name="want-to-know-more-about-pin-settings"></a>Vous voulez en savoir plus sur les paramètres de code confidentiel ?

- Les broches peuvent comporter de 4 à 12 chiffres ; la valeur par défaut est 5. Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels. Les lettres et les caractères spéciaux ne sont pas autorisés.
    
- Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur de Microsoft teams n’a pas encore commencé la réunion. Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.
    
- Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
