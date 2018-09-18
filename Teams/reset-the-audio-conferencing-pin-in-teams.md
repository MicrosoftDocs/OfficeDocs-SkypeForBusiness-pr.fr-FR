---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser dans Microsoft Teams. '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892953"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code composé de chiffres qui est créé pour chaque utilisateur de Microsoft Teams activé pour l’audioconférence. Les codes confidentiels d’audioconférence permettent aux organisateurs de réunions de s'identifier en tant que tels et de commencer une réunion téléphonique. S'ils utilisent l’application Microsoft Teams pour commencer la réunion, un code confidentiel n'est pas obligatoire. Si un utilisateur oublie son code confidentiel et qu'il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l'activer pour l’audioconférence, un administrateur peut le réinitialiser ou l’utilisateur peut réinitialiser son propre code confidentiel.
  
Les réunions peuvent commencer lorsqu'un utilisateur authentifié les rejoint en utilisant l’application Microsoft Teams ou lorsque l'organisateur saisit son code confidentiel à l'aide du téléphone pour participer. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Laisser un utilisateur réinitialiser son propre code confidentiel

1. L’utilisateur doit accéder à [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Cliquez sur **Réinitialiser le code confidentiel**. 


## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois réinitialisé par un administrateur, le code confidentiel s'affiche sous la forme ***********.
    
- L'envoi automatique de courrier électronique aux utilisateurs est activé par défaut, et les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront activés pour l’audioconférence ou lorsque le code confidentiel sera réinitialisé. Si vous avez désactivé l'envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé à l'utilisateur, ce qui vous obligera à lui envoyer manuellement.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, il reçoit un message électronique qui contient les informations sur la conférence et son code confidentiel. L'utilisateur doit posséder une boîte aux lettres Office 365, car lorsqu'un code confidentiel est réinitialisé, un nouveau code confidentiel lui est envoyé dans un courrier électronique à l'adresse SMTP principale (alias) qui lui est associée.
    
- Lorsque vous configurez l’audioconférence, vous définissez les codes confidentiels numériques de votre entreprise. Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s'applique uniquement aux nouveaux codes confidentiels générés et ne s'applique pas au paramètre de code confidentiel pour les utilisateurs déjà activés pour l’audioconférence. Reportez-vous à la section [Définir la longueur du code confidentiel pour les réunions d'audioconférence](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- L'adresse e-mail par défaut sera définie sur l'adresse SMTP principale Office 365 de l'utilisateur. Vous pouvez envoyer un message électronique à une adresse autre qu’une adresse Office 365 (Hotmail ou MSN par exemple). Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
