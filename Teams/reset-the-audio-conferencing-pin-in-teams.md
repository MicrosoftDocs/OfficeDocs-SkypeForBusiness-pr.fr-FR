---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment réinitialiser le code confidentiel de l’audioconférence d’un utilisateur dans Microsoft teams et comment découvrir des informations importantes sur les codes confidentiels.
ms.openlocfilehash: 8926218c72c888edb00480ff8382672a3730cf15
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666186"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code composé de chiffres qui est créé pour chaque utilisateur de Microsoft Teams activé pour l’audioconférence. Les codes confidentiels d’audioconférence permettent aux organisateurs de réunions de s'identifier en tant que tels et de commencer une réunion téléphonique. S'ils utilisent l’application Microsoft Teams pour commencer la réunion, un code confidentiel n'est pas obligatoire. Si un utilisateur oublie son code confidentiel et qu'il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l'activer pour l’audioconférence, un administrateur peut le réinitialiser ou l’utilisateur peut réinitialiser son propre code confidentiel.
  
Les réunions peuvent commencer lorsqu'un utilisateur authentifié les rejoint en utilisant l’application Microsoft Teams ou lorsque l'organisateur saisit son code confidentiel à l'aide du téléphone pour participer. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **modifier**.

3. Sous **audioconférence**, cliquez sur **Réinitialiser le code confidentiel**.

4. Cliquez sur **Réinitialiser**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Réinitialisation par un utilisateur de son propre code confidentiel

1. Demander à l’utilisateur d’accéder à [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Cliquez sur **Réinitialiser le code confidentiel**. 


## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Après la réinitialisation de votre code confidentiel par un administrateur, le code confidentiel sera répertorié comme suit :
    
- L’envoi automatique de courriers électroniques à des utilisateurs est activé par défaut, et les utilisateurs reçoivent un message électronique contenant leur code confidentiel lorsqu’ils sont activés pour les conférences audio ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel n’est pas envoyé à l’utilisateur et vous devrez lui envoyer manuellement les informations sur le code confidentiel.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Par défaut, les appelants anonymes ne permettent pas de démarrer une réunion.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, il est envoyé par défaut des messages électroniques qui incluent des informations de conférence et leur code confidentiel. L’utilisateur doit posséder une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code secret est envoyé à l’utilisateur dans un message électronique à l’adresse SMTP principale (alias) qui est définie pour l’utilisateur.
    
- Lorsque vous configurez l’audioconférence, vous définissez les chiffres requis pour les broches de votre organisation. Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, ce paramètre n’est appliqué qu’aux codes confidentiels générés et ne s’applique pas au paramètre code confidentiel pour les utilisateurs existants qui sont activés pour les conférences audio. Reportez-vous [à la section définir la longueur du code confidentiel pour les réunions de conférence audio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- Par défaut, l’adresse électronique est définie sur l’adresse SMTP principale de Microsoft 365 ou Office 365. Vous pouvez envoyer un courrier électronique à une adresse non Microsoft 365 ou non-Office 365 telle qu’une adresse de messagerie Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cette fonctionnalité est utile si les utilisateurs ne disposent pas de boîte aux lettres Exchange dans Microsoft 365 ou Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
