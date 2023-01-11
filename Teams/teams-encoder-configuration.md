---
title: Configuration de l’encodeur pour le streaming dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Cet article traite de la configuration RTMP basée sur l’encodeur pour les événements de streaming Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767946"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Configuration d’encodeurs pour le streaming d’événements en direct dans Microsoft Teams

Teams accepte les flux en direct d’une variété d’encodeurs différents qui génèrent RTMP ou RTMPS. Chaque encodeur étant différent, veillez à suivre les instructions relatives aux configurations d’encodeur lors de l’envoi à Teams.

Pour savoir comment configurer un événement en direct dans Teams, consultez création d’événements en direct. Si vous utilisez déjà un encodeur intégré à Teams, découvrez [comment configurer des encodeurs pour la diffusion en continu en direct](teams-encoder-setup.md).

## <a name="configuration-steps"></a>Étapes de configuration

Une fois que vous avez planifié l’événement en direct à l’aide de Teams ou Yammer et sélectionné l’option **Encodeur Teams** , vous pouvez récupérer l’URL et la clé RTMP de l’invitation à la réunion et les utiliser pour envoyer le flux dans l’interface utilisateur du producteur Teams.

### <a name="gather-the-rtmp-information"></a>Collecter les informations RTMP

#### <a name="scheduled-in-teams"></a>Planifié dans Teams

1. Ouvrez le client Teams et accédez au **calendrier**.
1. Sélectionnez l’événement en direct planifié et sélectionnez le bouton flèche double pour afficher les détails de l’invitation.
1. Accédez à la section **RTMP dans les détails** .
1. Sélectionnez le lien **Obtenir RTMP** pour copier l’URL d’ingestion RTMP dans le Presse-papiers.
1. Sélectionnez **Obtenir la clé RTMP** pour copier la clé RTMP dans le Presse-papiers.

#### <a name="scheduled-in-yammer"></a>Planifié dans Yammer

1. Accédez à la communauté Yammer où l’événement a été planifié.
1. Sélectionnez l’onglet **Événements** pour afficher les événements planifiés à venir.
1. Sélectionnez l’événement souhaité pour afficher la page de détails.
1. Sur le côté droit, sous **Produire**, sélectionnez le lien **informations RTMP** pour exposer l’URL et la clé RTMP.

## <a name="encoder-setup"></a>Configuration de l’encodeur

1. Une fois que vous avez collecté les informations RTMP, vérifiez que votre encodeur est configuré avec les paramètres appropriés conformément aux paramètres d’encodeur recommandés ci-dessous.
1. Entrez l’URL RTMP et la clé dans les paramètres de diffusion en continu de votre encodeur (reportez-vous à la documentation du fabricant pour plus d’informations).
1. Configurez votre encodeur avec les sources audio et vidéo souhaitées.
1. Ouvrez le client Teams et rejoignez l’évent en direct en tant que producteur.
1. Démarrez la diffusion en continu de l’encodeur vers l’URL d’ingestion RTMP Teams.
1. Dans la fenêtre Teams Producer, après quelques secondes, le flux RTMP de l’encodeur s’affiche dans la zone du présentateur.
1. Cliquez sur le flux RTMP dans la zone présentateur pour le placer dans la file d’attente sur le côté gauche.
1. Une fois que vous êtes satisfait du flux, sélectionnez **Envoyer en direct** . Le flux s’affiche également sur le côté droit de la fenêtre Producteur.
1. Sélectionnez **Démarrer** pour commencer le flux.

## <a name="recommended-encoder-settings"></a>Paramètres d’encodeur recommandés

### <a name="ingest-protocols"></a>Protocoles d’ingestion

- Vitesse de transmission unique RTMPS ou RTMP

### <a name="video-format"></a>Format vidéo

- Codec : H.264
- Profil : Élevé (niveau 4.0)
- Vitesse de transmission : jusqu’à 5 Mbits/s (5 000 Kbits/s)
- Vitesse de transmission constante stricte (CBR)
- Image clé/GOP : 2 secondes
  - Il doit y avoir une trame IDR au début de chaque GOP
  - Fréquence d’images : 29,97 i/s ou 30 images/s
  - Résolution : 1280 x 720 (720P)
  - Mode entrelacé : progressif

### <a name="audio-format"></a>Format audio

- Codec : AAC (LC)
- Vitesse de transmission : 192 Kbits/s
- Taux d’échantillonnage : 48 kHz ou 44,1 kHz (recommandé 48 kHz)

### <a name="playback-requirements"></a>Conditions requises pour la lecture

- Un flux audio et vidéo doit être présent pour lire du contenu dans Teams.

### <a name="configuration-tips"></a>Conseils de configuration

- Dans la mesure du possible, utilisez une connexion Internet câblée.
- Lorsque vous déterminez les besoins en bande passante, vous devez doubler les débits binaires de streaming. Bien qu’il ne s’agit pas d’une exigence obligatoire, elle contribuera à atténuer l’impact de la congestion du réseau.
- Lorsque vous utilisez des encodeurs logiciels, fermez tous les programmes inutiles.
- Ne modifiez pas votre configuration d’encodeur une fois qu’il a commencé à envoyer (push). Elle a des effets négatifs sur l’événement et peut rendre l’événement instable. Si vous souhaitez effectuer cette opération avant le démarrage de l’événement, vous devez vous déconnecter à l’aide des contrôles de producteur dans Teams et redémarrer l’installation.
- Si l’encodeur est déconnecté pendant l’événement en direct, reconnectez-le en conservant les mêmes horodatages que le processus en cours. Toute discontinuité peut entraîner des problèmes audio ou vidéo sur certains navigateurs et appareils.
- Accordez-vous suffisamment de temps pour configurer votre événement. Pour les événements à grande échelle, il est recommandé de démarrer la configuration une heure avant votre événement.
