---
title: Configurer la fonctionnalité M’appeler pour vos utilisateurs
author: SerdarSoysal
ms.author: serdars
ms.reviewer: 'macai, phedry'
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité M’appeler dans Teams afin que les utilisateurs ne peuvent pas rejoindre la partie audio par téléphone lorsqu’ils utilisent leur ordinateur pour l’audio.
ms.localizationpriority: medium
ms.collection:
  - M365-voice
f1.keywords:
  - NOCSH
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-mar2020
---

# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurer la fonctionnalité M’appeler pour vos utilisateurs

Dans Microsoft Teams, la fonctionnalité **M’appeler** permet aux utilisateurs d’rejoindre la partie audio d’une réunion par téléphone. Cela est utile dans les cas où l’utilisation d’un ordinateur pour l’audio n’est peut-être pas possible. Les utilisateurs peuvent obtenir la partie audio&mdash; de la réunion via leur téléphone portable ou leur ligne téléphonique ainsi que la partie contenu de la réunion, comme lorsqu’un autre participant&mdash; partage son écran ou lit une vidéo de présentation de leur ordinateur.

> [!IMPORTANT]
> 
> Pendant les périodes de forte affluence de réunions (que nous avons connues en liaison avec l'épidémie COVID-19), il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton <strong>Rejoindre une réunion Teams</strong> plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option <strong>M’appeler au</strong>. Cela contribuera à garantir la qualité audio pendant les heures au cours desquelles le grand nombre de réunions entraîne une congestion du réseau PSTN.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>Expérience utilisateur

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Participer à une réunion en utilisant un téléphone pour le son

Cliquez **sur** Rejoindre pour participer à une réunion, Téléphone **sur** l’écran Choisir vos **options audio et vidéo**, puis cliquez **sur Rejoindre maintenant**. À partir de là, les utilisateurs peuvent avoir l’appel de réunion et les rejoindre, ou se joindre manuellement à la réunion.

![Capture d’écran de l Téléphone l’option Audio.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Laisser la réunion Teams un appel**

Dans **l’écran Utiliser le téléphone pour l’audio** , l’utilisateur entre son numéro de téléphone, puis clique sur **M’appeler**. La réunion appelle l’utilisateur et l’intègre à la réunion.

![Capture d’écran de l’option M’appeler sur l’écran Utiliser le téléphone pour l’audio.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Se composer manuellement**

Vous pouvez également rejoindre la réunion par numérotation directe. Dans **l’écran Utiliser le téléphone pour la partie audio**, cliquez sur Composer manuellement pour obtenir la liste des numéros de téléphone à utiliser pour se rendre à la réunion.

![Capture d’écran de l’option Composer manuellement.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Recevez un appel en cas de problème audio pendant une réunion

Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur au cours d’une réunion, il peut facilement passer à son téléphone pour l’audio. Teams détecte quand un problème audio ou appareil se produit et redirige l’utilisateur vers son téléphone en affichant une option **Me** rappeler.

Voici un exemple du message et de l’option **Me** rappeler qui s’affiche quand Teams ne détecte pas de microphone.

![Capture d’écran de l’option Me rappeler.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L’utilisateur clique **sur Me rappeler**, ce qui affiche l’écran Utiliser **le téléphone pour l’audio** . À partir de là, il peut entrer son numéro de téléphone et se faire appeler Teams réunion et rejoindre la réunion ou se composer manuellement de la réunion.

## <a name="set-up-the-call-me-feature"></a>Configurer la fonctionnalité M’appeler

Pour activer la fonctionnalité M’appeler pour les utilisateurs de votre organisation, les configurations suivantes doivent être configurées :

- L’audioconférence est activé pour les utilisateurs dans votre organisation qui planifier des réunions (organisateurs de réunions). Pour en savoir plus, consultez Configurer l’audioconférence pour [Teams](set-up-audio-conferencing-in-teams.md) et gérer les paramètres d’audioconférence d’un [utilisateur dans Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- L’organisateur de la réunion peut appeler à partir de réunions. Pour en savoir plus, [consultez La gestion des paramètres d’audioconférence d’un utilisateur dans Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Si les appels sortants des réunions ne sont pas activés pour l’organisateur de la réunion, l’option **audio Téléphone** dans l’écran Choisir vos **options audio** et vidéo n’est disponible pour personne et les autres utilisateurs ne peuvent pas recevoir d’appel pour participer à la réunion. Pour les utilisateurs dont l’appel sortant est activé, une fois qu’ils ont rejoint la réunion, ils peuvent rejoindre d’autres personnes composant leur numéro à partir de l’icône Afficher **les participants** .
