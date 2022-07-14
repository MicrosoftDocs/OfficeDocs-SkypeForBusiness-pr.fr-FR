---
title: Configurer la fonctionnalité M’appeler pour vos utilisateurs
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez comment configurer la fonctionnalité Appelez-moi dans Teams afin que les utilisateurs puissent rejoindre la partie audio par téléphone lorsque l’utilisation de leur ordinateur pour l’audio n’est peut-être pas possible.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794532"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Configurer la fonctionnalité M’appeler pour vos utilisateurs

Dans Microsoft Teams, la fonctionnalité **Appeler moi** permet aux utilisateurs de participer à la partie audio d’une réunion par téléphone. Cela est pratique dans les scénarios où l’utilisation d’un ordinateur pour l’audio peut ne pas être possible. Les utilisateurs obtiennent la partie audio de la réunion par le biais de leur téléphone cellulaire ou de la ligne terrestre, ainsi que la partie de contenu de la réunion, par exemple lorsqu’un autre participant à la réunion&mdash;partage son écran ou lit une vidéo&mdash;sur son ordinateur.

> [!IMPORTANT]
> 
> Pendant les périodes de forte affluence de réunions (que nous avons connues en liaison avec l'épidémie COVID-19), il est recommandé aux utilisateurs de rejoindre les réunions en cliquant sur le bouton <strong>Rejoindre une réunion Teams</strong> plutôt que de se connecter en utilisant les numéros de conférence RTC ou l’option <strong>M’appeler au</strong>. Cela contribuera à garantir la qualité audio pendant les heures au cours desquelles le grand nombre de réunions entraîne une congestion du réseau PSTN.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>Expérience utilisateur

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Participer à une réunion à l’aide d’un téléphone pour l’audio

Cliquez sur **Rejoindre** pour participer à une réunion, puis **sur Téléphone audio** sur l’écran **Choisir vos options vidéo et audio** , puis cliquez sur **Rejoindre maintenant**. À partir de là, les utilisateurs peuvent avoir l’appel de réunion et les rejoindre ou se connecter manuellement à la réunion.

![Capture d’écran de l’option Audio Phone.](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Autoriser l’appel de réunion Teams**

Sur l’écran **Utiliser le téléphone pour l’audio**, l’utilisateur entre son numéro de téléphone, puis clique sur **Appeler.** La réunion appelle l’utilisateur et le joint à la réunion.

![Capture d’écran de l’option Appeler moi sur l’écran Utiliser le téléphone pour l’audio.](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Connexion manuelle**

Une autre façon de participer consiste à se connecter directement à la réunion. Sur l’écran **Utiliser le téléphone pour l’audio** , cliquez sur **Composer manuellement** pour obtenir la liste des numéros de téléphone à utiliser pour vous connecter à la réunion.

![Capture d’écran de l’option Numérotation manuelle.](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Recevoir un rappel en cas de problème avec l’audio pendant une réunion

Si un utilisateur rencontre des problèmes audio lors de l’utilisation de son ordinateur pendant une réunion, il peut facilement passer à l’utilisation de son téléphone pour l’audio. Teams détecte quand un problème audio ou d’appareil se produit et redirige l’utilisateur pour utiliser son téléphone en affichant une option **Me rappeler** .

Voici un exemple du message et de l’option **Me rappeler** qui s’affiche lorsque Teams ne détecte pas de microphone.

![Capture d’écran de l’option Me rappeler.](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

L’utilisateur clique sur **Me rappeler**, ce qui fait apparaître l’écran **Utiliser le téléphone pour l’audio** . À partir de là, ils peuvent entrer leur numéro de téléphone et avoir l’appel de réunion Teams et les rejoindre à la réunion ou se connecter manuellement à la réunion.

## <a name="set-up-the-call-me-feature"></a>Configurer la fonctionnalité Appeler moi

Pour activer la fonctionnalité Appelez-moi pour les utilisateurs de votre organisation, les éléments suivants doivent être configurés :

- L’audioconférence est activée pour les utilisateurs de votre organisation qui planifient des réunions (organisateurs de réunions). Pour plus d’informations, consultez [Configurer l’audioconférence pour Teams](set-up-audio-conferencing-in-teams.md) et [gérer les paramètres d’audioconférence pour un utilisateur dans Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- L’organisateur de la réunion peut effectuer un appel sortant à partir de réunions. Pour plus d’informations, consultez [Gérer les paramètres d’audioconférence d’un utilisateur dans Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Si l’accès sortant des réunions n’est pas activé pour l’organisateur de la réunion, l’option **Audio téléphone** sur l’écran **Choisir vos options vidéo et audio** n’est disponible pour personne, et les autres utilisateurs ne peuvent pas recevoir d’appel pour les rejoindre à la réunion. Pour les utilisateurs avec accès sortant activé, une fois qu’ils ont rejoint la réunion, ils peuvent rejoindre d’autres personnes en numérotant leur numéro à partir de l’icône **Afficher les participants** .
