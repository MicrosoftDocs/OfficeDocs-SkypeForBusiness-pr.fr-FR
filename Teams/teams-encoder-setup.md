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
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767949"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Utilisation d’un encodeur pour le streaming en direct dans Microsoft Teams

Les encodeurs Teams permettent aux utilisateurs de produire des événements en direct directement à partir d’un encodeur matériel ou logiciel externe avec Microsoft Teams.

## <a name="overview"></a>Vue d’ensemble

Un encodeur prend du contenu audio et vidéo provenant de différentes sources que vous utilisez lors d’un événement en direct, comme une caméra, un microphone, une capture d’écran de bureau, etc. Il compresse et convertit ce média dans un format numérique approprié, puis l’envoie à Teams pour la diffusion en continu en direct à votre public. Consultez notre [playbook production personnalisée](https://aka.ms/CustomProductionVEP) pour en savoir plus sur la façon dont vous pouvez utiliser les technologies de production Teams (telles que NDI) avec des encodeurs externes.

## <a name="production-workflow-when-using-an-encoder"></a>Flux de travail de production lors de l’utilisation d’un encodeur

Le flux de travail pour la production d’un événement en direct Teams est le suivant :

Un événement en direct est planifié dans Teams ou Yammer, et l’option **Encodeur Teams** est sélectionnée. Cela provisionne un point de terminaison RTMP, qui est fourni avec une URL RTMP(S) et la clé correspondante. L’URL et la clé sont utilisées par l’encodeur pour se connecter au point de terminaison RTMP pour l’événement en direct planifié.

### <a name="common-encoders-user-with-live-events"></a>Utilisateur d’encodeurs courants avec des événements en direct

Les encodeurs des deux listes suivantes ont été testés par Microsoft pour la diffusion en continu en direct avec Teams. La première liste est un sous-ensemble de ces encodeurs, qui ont été testés avec le produit pour faciliter l’utilisation et la configuration rapide.

#### <a name="stream-ready-encoders"></a>Encodeurs prêts pour le flux

|Encodeur                                |Site web  |Détails  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |Fournit des vidéos HD de haute qualité avec Haivision Hub, une alternative puissante à RTMP. |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |Les encodeurs vidéo H.264 et HEV fournissent des cascades vidéo ABR de haute qualité pour des résolutions allant jusqu’à 4K. |
|Open Broadcaster Software (OBS Studio) |[Open Broadcaster Software](https://obsproject.com/) |Capture et mixage vidéo/audio en temps réel hautes performances, prenant en charge toutes les plateformes de diffusion en continu, et bien plus encore. |
|vMix                                   |[vMix](https://www.vmix.com/) |Mixeur vision logicielle qui contrôle l’enregistrement, le mixage et la diffusion en continu en direct de caméras, de vidéos, d’audio, etc. |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |Logiciel de diffusion web qui couvre toutes les bases + production multi-caméra. |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |Synchronise plusieurs appareils Apple avec une ou plusieurs caméras pour la capture et la modification vidéo en temps réel. |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |Enregistrement vidéo et audio en temps réel pour la diffusion en continu en direct sur des appareils connectés à Internet |
|Diffuseur XSplit                     |[Diffuseur XSplit](https://www.xsplit.com/) |Produit, mélange et fournit du contenu vidéo enrichi, y compris le gameplay pour la diffusion en continu en direct. |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |Suite de logiciels open source pour la gestion de fichiers vidéo, audio et autres fichiers multimédias et flux en direct. |
|Camion de production          |[Camion de production](https://www.blueframetech.com/productiontruck) |Filme et diffuse des événements sur place à partir d’un camion ou d’un camion mobile. |
|Producteur d’IA d’arena en direct                 |Producteur d’IA |Studio de production intégré à Microsoft Teams en tant qu’application de réunion.|
|StreamYard                             |StreamYard |Live Streaming Studio dans le navigateur.|
|Socialive                              |Socialive |Plateforme de production vidéo cloud, offrant une expérience tout-en-un pour la production et la distribution de contenu vidéo de qualité studio.|
|Brandlive                              |BrandLive |Plateforme de production basée sur le cloud.|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Encodeur Haivision Makito X et Encodeur Makito KB

Si vous disposez d’un encodeur Haivision X ou Makito KB existant, vous pouvez choisir l’option appropriée dans la liste déroulante et suivre la liste des instructions.

1. Sélectionnez **Démarrer l’installation** pour créer un canal pour la diffusion en continu en direct. Attendez la fin de l’installation. Un message **Prêt à se connecter** s’affiche à l’écran.
1. Une fois cette opération terminée, téléchargez la présélection qui contient tous les paramètres d’encodage, y compris l’URL d’ingestion et le nom de l’événement. Importez la présélection dans l’encodeur et démarrez l’encodeur.
1. Retour à Teams. Une fois que vous êtes en mesure de voir l’aperçu à partir de l’encodeur, sélectionnez **Démarrer l’événement** pour passer en ligne afin que votre public puisse voir l’événement en direct.

> [!NOTE]
> La prise en charge de Haivision KB Encoder pour RTMPS n’a pas encore été testée. Haivision Makito X Encoder ne prend pas en charge RTMPS. Les présélections téléchargées pour les deux encodeurs contiennent l’URL d’ingestion RTMP.

### <a name="switcher-studio"></a>Switcher Studio

Vous pouvez utiliser Switcher Studio pour commencer la diffusion en continu vers Teams à l’aide d’un iPhone ou d’un iPad.

1. Sélectionnez **Démarrer l’installation** pour créer un canal pour la diffusion en continu en direct. Attendez la fin de l’installation. Un message **Prêt à se connecter** s’affiche à l’écran.
2. Switcher Studio ouvre le tableau de bord Switcher Studio pour ajouter l’événement en direct à votre compte.

> [!NOTE]
> Si vous n’avez pas encore de compte Switcher Studio, vous devez en créer un).

3. Une fois cette opération terminée, vous pouvez accéder à votre application Switcher Studio sur votre iPhone ou iPad, sélectionner Teams sous l’onglet Sortie et commencer la diffusion en continu vers Teams.
4. Retour à Teams. Une fois que vous êtes en mesure de voir l’aperçu à partir de l’encodeur, sélectionnez **Démarrer l’événement** pour que votre public puisse voir l’événement en direct.

> [!NOTE]
> Switcher Studio utilise l’URL d’ingestion RTMP.

### <a name="wirecast"></a>Wirecast

Si vous êtes un utilisateur existant de Wirecast, vous pouvez choisir cette option dans la liste déroulante pour envoyer un flux en direct à Teams. Notez que vous aurez besoin de Wirecast version 10 ou ultérieure.

1. Sélectionnez **Démarrer l’installation** pour créer un canal pour la diffusion en continu en direct. Attendez la fin de l’installation. Un message **Prêt à se connecter** s’affiche à l’écran.
1. L’encodeur lance l’application Wirecast sur votre ordinateur préconfiguré avec les paramètres d’encodage corrects et l’URL d’ingestion pour cet événement en direct. Lorsque vous êtes prêt, cliquez sur l’icône Teams dans l’application Wirecast pour commencer la diffusion en continu vers Teams.
1. Retour à Teams. Une fois que vous êtes en mesure de voir l’aperçu à partir de l’encodeur, sélectionnez **Démarrer l’événement** pour que votre public puisse voir l’événement en direct.

> [!NOTE]
> L’application Wirecast est lancée avec l’URL d’ingestion RTMPS préconfigurée.
