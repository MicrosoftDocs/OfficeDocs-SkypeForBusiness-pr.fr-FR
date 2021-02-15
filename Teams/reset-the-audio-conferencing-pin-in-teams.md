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
description: Découvrez comment réinitialiser le code confidentiel d’un utilisateur pour l’audioconférence dans Microsoft Teams et apprenez les informations importantes sur les code confidentiels.
ms.openlocfilehash: 3f1055551edb45ac422052476196f01ee4d2765d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237464"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code composé de chiffres qui est créé pour chaque utilisateur de Microsoft Teams activé pour l’audioconférence. Les codes confidentiels d’audioconférence permettent aux organisateurs de réunions de s'identifier en tant que tels et de commencer une réunion téléphonique. S'ils utilisent l’application Microsoft Teams pour commencer la réunion, un code confidentiel n'est pas obligatoire. Si un utilisateur oublie son code confidentiel et qu'il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l'activer pour l’audioconférence, un administrateur peut le réinitialiser ou l’utilisateur peut réinitialiser son propre code confidentiel.
  
Les réunions peuvent être démarrées lorsqu’un utilisateur authentifié participe à l’aide de l’application Microsoft Teams ou lorsque l’organisateur participe avec son code confidentiel par téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez **sur Modifier.**

3. Sous **Audioconférence,** cliquez sur **Réinitialiser le code confidentiel.**

4. Cliquez sur **Réinitialiser.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Aider l’utilisateur à se rendre sur [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Cliquez sur **Réinitialiser le code confidentiel.** 


## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n’est présenté qu’une fois à un administrateur, lors de la réinitialisation du code confidentiel. Une fois le code confidentiel réinitialisé par un administrateur, il s’intitialise *********.
    
- L’envoi automatique de courriers électroniques aux utilisateurs est activé par défaut et les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel ne sera pas envoyé à l’utilisateur et vous de aurez à envoyer manuellement les informations de code confidentiel à l’utilisateur.
    
- Lorsqu’une réunion commence, tous les utilisateurs qui se retrouvent dans la salle d’accueil la rejoignent automatiquement. Par exemple, si deux participants essaient de rejoindre une réunion avant qu’elle ait commencé, ils sont placés dans la salle d’attente et écoutent de la musique pendant la mise en attente, et lorsque l’organisateur de la réunion rejoint la réunion à l’aide de son code confidentiel par téléphone, la réunion commence et les participants dans la salle d’attente rejoignent la réunion.
    
- Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, il est envoyé par défaut pour recevoir des courriers électroniques qui incluent les informations sur la conférence et son code confidentiel. L’utilisateur doit avoir une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur par courrier électronique à son adresse SMTP principale (alias) définie pour l’utilisateur.
    
- Lorsque vous définissez l’audioconférence, vous définissez les chiffres requis pour les codex pin de votre organisation. Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s’applique uniquement aux nouveaux code confidentiels générés et ne s’applique pas au paramètre de code confidentiel pour les utilisateurs déjà activés pour l’audioconférence. Consultez [la longueur du code confidentiel pour les réunions d’audioconférence.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- Par défaut, le courrier électronique sera réglé sur l’adresse SMTP principale Microsoft 365 ou Office 365 de l’utilisateur. Vous pouvez envoyer un courrier électronique à une adresse non Microsoft 365 ou non-Office 365 telle qu’une adresse de messagerie Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Ceci est utile si les utilisateurs n’ont pas de boîte aux lettres Exchange dans Microsoft 365 ou Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
