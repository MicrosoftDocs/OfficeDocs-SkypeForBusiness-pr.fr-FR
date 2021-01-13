---
title: Configurer la fonctionnalité M’appeler pour vos utilisateurs
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité M’appeler dans Teams afin que les utilisateurs ne peuvent pas rejoindre la partie audio par téléphone lorsqu’ils utilisent leur ordinateur pour l’audio.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821094"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurer la fonctionnalité M’appeler pour vos utilisateurs

Dans Microsoft Teams, la fonctionnalité **M’appeler** permet aux utilisateurs de rejoindre la partie audio d’une réunion par téléphone. Cela est utile dans les cas où l’utilisation d’un ordinateur pour l’audio n’est peut-être pas possible. Les utilisateurs peuvent obtenir la partie audio de la réunion via leur téléphone portable ou leur ligne téléphonique ainsi que la partie contenu de la réunion, par exemple lorsqu’un autre participant partage son écran ou lit une vidéo sur leur &mdash; &mdash; ordinateur.

> [!IMPORTANT]
> 
> Pendant les périodes de forte affluence de réunions (que nous avons connues en liaison avec l'épidémie COVID-19), il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton <strong>Rejoindre une réunion Teams</strong> plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option <strong>M’appeler au</strong>. Cela contribuera à garantir la qualité audio pendant les heures au cours desquelles le grand nombre de réunions entraîne une congestion du réseau PSTN. 

> [!IMPORTANT]
> Pendant la durée de l’épidémie COVID-19, il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton **Rejoindre une réunion Teams** plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option **M’appeler au**</strong>. Cela est principalement dû à l’encombrement des infrastructures téléphonique des pays touchés par le COVID-19. En évitant les appels RTC, vous bénéficierez probablement d’une meilleure qualité audio. 

## <a name="the-user-experience"></a>Expérience utilisateur

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Participer à une réunion en utilisant un téléphone pour le son

Cliquez **sur** Rejoindre pour participer à une réunion, puis sur **Audio** sur l’écran Choisir vos  **paramètres audio et** vidéo. À partir de là, les utilisateurs peuvent avoir l’appel de réunion et les rejoindre, ou se joindre manuellement à la réunion.

![Capture d’écran de l’option Audio du téléphone](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Laisser la réunion Teams appeler**

Sur **l’écran Utiliser le téléphone pour l’audio,** l’utilisateur entre son numéro de téléphone, puis clique sur **M’appeler.** La réunion appelle l’utilisateur et l’intègre à la réunion.

![Capture d’écran de l’option M’appeler sur l’écran Utiliser le téléphone pour l’audio](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Se composer manuellement**

Vous pouvez également rejoindre la réunion par numérotation directe. Dans **l’écran Utiliser le téléphone pour la partie audio,** cliquez sur Composer manuellement pour obtenir la liste des numéros de téléphone à utiliser pour se rendre à la réunion. 

![Capture d’écran de l’option Composer manuellement](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Recevez un appel en cas de problème audio pendant une réunion

Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, il peut facilement passer à son téléphone pour l’audio. Teams détecte un problème audio ou d’appareil et redirige l’utilisateur vers son téléphone en affichant une option **Me** rappeler.

Voici un exemple du message  et de l’option Me rappeler qui s’affiche lorsque Teams ne détecte pas de microphone.

![Capture d’écran de l’option Me rappeler](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L’utilisateur clique **sur Me rappeler,** ce qui affiche l’écran Utiliser **le téléphone pour l’audio.** À partir de là, il peut entrer son numéro de téléphone, lancer l’appel de la réunion Teams et le joindre à la réunion ou se joindre manuellement à la réunion.

## <a name="set-up-the-call-me-feature"></a>Configurer la fonctionnalité M’appeler

Pour activer la fonctionnalité M’appeler pour les utilisateurs de votre organisation, les configurations suivantes doivent être configurées :

- L’audioconférence est activé pour les utilisateurs dans votre organisation qui planifier des réunions (organisateurs de réunions). Pour en savoir plus, consultez Configurer l’audioconférence pour [Teams](set-up-audio-conferencing-in-teams.md) et gérer les paramètres d’audioconférence pour [un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Les utilisateurs peuvent appeler à partir des réunions. Pour en savoir plus, [consultez Gérer les paramètres d’audioconférence d’un utilisateur dans Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Si un utilisateur n’a pas activé les  appels sortants des réunions, l’option M’appeler n’est pas disponible et l’utilisateur ne recevra pas d’appel pour participer à la réunion. À la place, l’utilisateur voit sur l’écran Utiliser le téléphone pour **l’audio** une liste qui lui permet de se composer manuellement de la réunion sur son téléphone.
