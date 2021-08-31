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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Découvrez comment réinitialiser le code confidentiel d’audioconférence d’un utilisateur dans Microsoft Teams comment consulter des informations importantes sur les code confidentiels.
ms.openlocfilehash: 206d625fdf656af5c4b30fdcc9f87dae760807cd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730093"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code composé de nombres qui est créé pour Microsoft Teams utilisateur activé pour l’audioconférence. Les conférences audioconférences sont utilisées par les organisateurs de la réunion pour identifier qu’ils en sont l’organisateur et les autoriser à démarrer une réunion par téléphone. S’il utilise l Microsoft Teams de messagerie pour commencer la réunion, le code confidentiel n’est pas nécessaire. Si un utilisateur oublie son code confidentiel et qu’il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l’audioconférence, un administrateur peut réinitialiser son code confidentiel ou réinitialiser son code confidentiel.
  
Les réunions peuvent être démarrées lorsqu’un utilisateur authentifié rejoint la réunion à l’aide de l’application Microsoft Teams ou lorsque l’organisateur participe avec son code confidentiel sur le téléphone. Lorsqu’une réunion nécessite un code confidentiel pour commencer, les utilisateurs qui rejoignent la réunion par téléphone sont placés dans la salle d’attente et écoutent de la musique mise en attente jusqu’à ce que l’organisateur les admette. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

![Icône représentant le Microsoft Teams logo.](media/teams-logo-30x30.png) **Utiliser le centre d’administration Microsoft Teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez **sur Modifier.**

3. Sous **Audioconférence,** cliquez sur **Réinitialiser le code confidentiel.**

4. Cliquez sur **Réinitialiser.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Aider l’utilisateur à se rendre sur [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Cliquez sur **Réinitialiser le code confidentiel.** 

> [!NOTE]
> Pour GCCH, voir https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing :

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n’est présenté qu’une fois à un administrateur, lors de la réinitialisation du code confidentiel. Une fois le code confidentiel réinitialisé par un administrateur, il s’intitialise *********.
    
- L’envoi automatique de courriers électroniques aux utilisateurs est activé par défaut et les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel ne sera pas envoyé à l’utilisateur et vous de aurez à envoyer manuellement les informations de code confidentiel à l’utilisateur.
    
- Lorsqu’une réunion commence, l’organisateur doit admettre tous les utilisateurs PSTN dans la salle d’accueil pour rejoindre la réunion. Par exemple, si deux participants PSTN essaient de rejoindre une réunion avant qu’elle ait commencé, ils sont placés dans la salle d’attente et écoutent de la musique en attente, et lorsque l’organisateur de la réunion rejoint la réunion à l’aide de son code confidentiel par téléphone, la réunion commence et l’organisateur peut utiliser la commande pendant la réunion (appuyez sur *21) pour admettre tous les utilisateurs PSTN dans la salle d’attente.
    
- Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.
    
- Lorsque vous activez l’audioconférence pour un utilisateur, celui-ci est envoyé par défaut par courrier électronique qui inclut les informations sur la conférence et son code confidentiel. L’utilisateur doit avoir une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur par courrier électronique à son adresse SMTP principale (alias) définie pour l’utilisateur.
    
- Lorsque vous définissez l’audioconférence, vous définissez les chiffres requis pour les codex pin de votre organisation. Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s’applique uniquement aux nouveaux code confidentiels générés et ne s’applique pas au paramètre de code confidentiel pour les utilisateurs déjà activés pour l’audioconférence. Consultez [la longueur du code confidentiel pour les réunions d’audioconférence.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- Par défaut, l’e-mail est Microsoft 365 ou Office 365 adresse SMTP principale de l’utilisateur. Vous pouvez envoyer un courrier électronique à une adresse de courrier non Microsoft 365 ou non Office 365 telle qu’une adresse de messagerie Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Ceci est utile si les utilisateurs n’ont pas de boîte aux lettres Exchange messagerie dans Microsoft 365 ou Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
