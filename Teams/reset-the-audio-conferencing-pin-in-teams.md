---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser dans Microsoft Teams. '
ms.openlocfilehash: 292cc1c042816236fed35b536dd529b49e902203
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347497"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code constitué de numéros sont créées pour chaque utilisateur de Microsoft Teams qui est activé pour l’audioconférence. Codes confidentiels de conférence audio sont utilisés par les organisateurs de réunion pour identifier qu’ils sont l’organisateur de la réunion et de démarrer une réunion par téléphone. S’ils utilisent l’application Microsoft Teams pour démarrer la réunion, un code confidentiel n’est pas obligatoire. Si les utilisateurs oublient leur code confidentiel et qu’ils ne peut pas trouver dans le courrier électronique qui a été envoyé lorsqu’ils ont été activés pour l’audioconférence, un administrateur peut réinitialiser leur code confidentiel, ou ils peuvent réinitialiser leur propre code confidentiel.
  
Réunions peuvent être démarrées lorsqu’un utilisateur authentifié se joint à l’aide de l’application Microsoft Teams ou lorsque l’organisateur de jointures avec son code confidentiel sur le téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) À l’aide de Skype les équipes Microsoft Business centre d’administration

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **Modifier**.

3. **Conférence Audio**, cliquez sur **Réinitialiser le code confidentiel**.

4. Cliquez sur **Réinitialiser**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Réinitialisation par un utilisateur de son propre code confidentiel

1. Demandez à l’utilisateur d’accéder à [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Cliquez sur **Réinitialiser le code confidentiel**. 


## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois que le code confidentiel est réinitialisé par un administrateur, le code confidentiel est répertorié comme ***.
    
- Envoyer automatiquement des messages électroniques aux utilisateurs est activée par défaut, et les utilisateurs reçoivent un message électronique avec leur code confidentiel lorsqu’elles sont activées pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé à un utilisateur et vous devez envoyer manuellement les informations de code confidentiel à l’utilisateur.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Le paramètre par défaut n’autorise ne pas une réunion doit être démarré par les appelants anonymes.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, par défaut, ils sont envoyés les messages électroniques qui incluent des informations de conférence et de leur code confidentiel. L’utilisateur doit avoir une boîte aux lettres Office 365, étant donné que lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l’utilisateur dans le message électronique à leur adresse SMTP principale (alias) est définie pour l’utilisateur.
    
- Lorsque vous configurez les services d’audioconférence, vous définissez les chiffres qui sont requis pour les codes confidentiels dans votre organisation. Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur de code confidentiel, le paramètre est appliqué uniquement sur les codes confidentiels nouvellement créés et n’est pas appliqué au paramètre code confidentiel pour les utilisateurs existants qui sont activées pour l’audioconférence. Voir [définir la longueur de l’axe des réunions de conférence Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Le courrier électronique par défaut est fixé à l’adresse SMTP principale d’Office 365 de l’utilisateur. Vous pouvez envoyer un message électronique à une adresse non Office 365 tels que Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
