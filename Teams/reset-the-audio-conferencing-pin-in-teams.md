---
title: Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
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
description: Découvrez comment réinitialiser le code confidentiel d’audioconférence d’un utilisateur dans Microsoft Teams et découvrir des faits importants sur les codes confidentiels.
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329028"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Réinitialiser le code confidentiel d’audioconférence dans Microsoft Teams

Un code confidentiel est un code composé de nombres créés pour chaque utilisateur Microsoft Teams activé pour l’audioconférence. Les codes confidentiels d’audioconférence sont utilisés par les organisateurs de réunion pour identifier qu’ils sont l’organisateur de la réunion et leur permettre de démarrer une réunion par téléphone. S’ils utilisent l’application Microsoft Teams pour démarrer la réunion, aucun code confidentiel n’est nécessaire. Si les utilisateurs oublient leur code confidentiel et qu’ils ne le trouvent pas dans l’e-mail qui leur a été envoyé lorsqu’ils ont été activés pour l’audioconférence, un administrateur peut réinitialiser leur code confidentiel ou réinitialiser leur propre code confidentiel.
  
Les réunions peuvent être démarrées lorsqu’un utilisateur authentifié rejoint à l’aide de l’application Microsoft Teams ou lorsque l’organisateur joint son code confidentiel par téléphone. Lorsqu’une réunion nécessite le démarrage d’un code confidentiel, les utilisateurs qui se joignent par téléphone sont placés dans la salle d’attente et écoutent de la musique en attente jusqu’à ce que l’organisateur les admette. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.

## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

Utilisation du Centre d’administration Microsoft Teams :

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**.

4. Cliquez sur **Réinitialiser**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>Faire réinitialiser son propre code confidentiel

1. Que l’utilisateur accède à [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp).
2. Cliquez sur **Réinitialiser le code confidentiel**.

> [!NOTE]
> Pour GCCH, accédez à : [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp).
> Pour DoD, accédez à : [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp).

> [!NOTE]
> Un e-mail de réinitialisation de code confidentiel n’est pas envoyé à l’utilisateur si vous utilisez cette méthode.

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n’est présenté qu’une seule fois à un administrateur, lorsque le code confidentiel est réinitialisé. Une fois le code confidentiel réinitialisé par un administrateur, il est répertorié comme *********.

- L’envoi automatique d’e-mails aux utilisateurs est activé par défaut et les utilisateurs reçoivent un e-mail avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique d’e-mails, aucun e-mail de réinitialisation du code confidentiel n’est envoyé à un utilisateur et vous devrez envoyer manuellement les informations de code confidentiel à l’utilisateur.

- Lorsqu’une réunion démarre, l’organisateur doit admettre tous les utilisateurs RTC dans la salle d’attente pour participer à la réunion. Par exemple, si deux participants RTC tentent de rejoindre une réunion avant son démarrage, ils sont placés dans la salle d’attente et écoutent de la musique en attente, et lorsque l’organisateur de la réunion rejoint à l’aide de son code confidentiel par téléphone, la réunion démarre et l’organisateur peut utiliser la commande en réunion (appuyez sur *21) pour admettre tous les utilisateurs RTC dans la salle d’attente.

- Le paramètre par défaut est de ne pas autoriser le démarrage d’une réunion par des appelants anonymes.

- Lorsque vous activez un utilisateur pour l’audioconférence, par défaut, il est envoyé des e-mails qui incluent des informations de conférence et son code confidentiel. L’utilisateur doit disposer d’une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur par e-mail à son adresse SMTP principale (alias) définie pour l’utilisateur.

- Lorsque vous configurez l’audioconférence, vous définissez les chiffres requis pour les codes confidentiels de votre organisation. Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, ce paramètre est appliqué uniquement aux codes confidentiels nouvellement générés et n’est pas appliqué au paramètre de code confidentiel pour les utilisateurs existants qui sont activés pour l’audioconférence. Voir [Définir la longueur du code confidentiel pour les réunions d’audioconférence](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).

- L’e-mail par défaut est défini sur l’adresse SMTP principale de Microsoft 365 ou Office 365 de l’utilisateur. Vous pouvez envoyer un e-mail à une adresse non-Microsoft 365 ou non Office 365 telle qu’une adresse e-mail Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs n’ont pas de boîte aux lettres Exchange dans Microsoft 365 ou Office 365.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user-in-teams.md)
