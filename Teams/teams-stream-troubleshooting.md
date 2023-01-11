---
title: Résolution des problèmes de diffusion en direct dans Microsoft Teams
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
description: Cet article décrit les options de résolution des problèmes pour les événements de streaming Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: d88b8c0f356bcf59319f073c0e75c65a25361cf2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767953"
---
# <a name="troubleshooting-live-events-in-microsoft-teams"></a>Résolution des problèmes liés aux événements en direct dans Microsoft Teams

> [!IMPORTANT]
> **Chine** : les utilisateurs situés en Chine ne seront pas en mesure de configurer ou d’assister à des événements en direct Teams ou Yammer ou de regarder des vidéos à la demande, car actuellement, Azure CDN, sur lequel ces applications s’appuient, peut ne pas être accessible en Chine.
>
> En tant qu’administrateur, vous devrez peut-être configurer un VPN pour connecter votre réseau d’entreprise pour que ces applications fonctionnent en toute transparence. Une fois cette opération terminée, les membres de votre organisation peuvent planifier et participer à des événements en direct.

## <a name="before-a-live-event"></a>Avant un événement en direct

### <a name="make-sure-all-events-are-reachable-in-your-network"></a>Assurez-vous que tous les événements sont accessibles dans votre réseau

#### <a name="general-teams-endpoints"></a>Points de terminaison Teams généraux

Teams nécessite une connectivité à Internet. Tous les points de terminaison [répertoriés sur Office 365 points de terminaison pour Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) doivent être accessibles par les utilisateurs de Teams au sein du réseau de votre organisation.

#### <a name="teams-encoder-live-events---rmtp-ingest-endpoints"></a>Événements en direct de l’encodeur Teams - Points de terminaison d’ingestion RMTP

Pour obtenir un flux vidéo pour un événement en direct Encodeur Teams envoyé à Teams à partir de votre encodeur, vous avez besoin du nom de domaine et des ports ouverts dans le pare-feu de votre réseau :

- Domaines : *.rtmpingest.mcr.teams.microsoft.com
- Ports : 1935/1936 (pour RTMP/RTMPS)

### <a name="make-sure-you-have-enough-upload-bandwidth"></a>Vérifiez que vous disposez d’une bande passante de chargement suffisante

Lors de la production ou de la diffusion en continu d’un événement en direct via RTMP, il est possible que la bande passante de chargement Internet sur le site qui envoie le flux en direct ne soit pas suffisante. Une bande passante de chargement faible peut entraîner la suppression d’images ou des problèmes dans la vidéo en direct elle-même, ce qui peut entraîner des problèmes de lecture pour les téléspectateurs.

Assurez-vous que la vitesse de chargement de la machine et du réseau qui envoie le flux en direct est supérieure à la vitesse de transmission que vous avez définie pour le flux en direct. Si vous envoyez un flux de 5 Mbits/s à partir de votre encodeur, mais que votre débit de chargement est proche ou inférieur à celui-ci, vous risquez de rencontrer des problèmes de ne pas pouvoir charger votre flux assez rapidement.

Si vous rencontrez des problèmes de bande passante de chargement, voici quelques solutions que vous pouvez essayer :

1. Utilisez une connexion Ethernet câblée en dur pour n’importe quelle machine à partir de laquelle vous poussez le flux afin d’éviter toute chute dans le Wi-Fi.
1. Réduisez la vitesse de transmission d’encodage de votre flux en direct à une valeur bien inférieure à votre vitesse de chargement maximale.

### <a name="preparing-your-network-for-many-concurrent-viewers"></a>Préparation de votre réseau pour de nombreuses visionneuses simultanées

Pendant les événements en direct, de nombreuses personnes se joindront pour regarder votre événement en direct. Cela peut mettre une pression sur votre réseau et la bande passante de téléchargement Internet. Vous devez évaluer votre infrastructure réseau actuelle et vous assurer que les membres de votre réseau d’entreprise disposent de la bande passante nécessaire pour regarder un événement en direct. Pour réduire le trafic Internet nécessaire pour les événements en direct, deux options s’offrent à vous :

1. Configurez des proxys de cache existants au sein de votre réseau pour mettre en cache des vidéos à partir de Teams.
1. Utilisez une solution de diffusion vidéo eCDN tierce pour optimiser le trafic vidéo.

### <a name="i-cant-create-a-live-event"></a>Je ne parviens pas à créer un événement en direct

Microsoft Teams et Yammer disposent d’autorisations permettant à un utilisateur de créer un événement en direct en fonction du service que vous utilisez pour l’événement en direct.

1. Vérifiez que l’administrateur Teams vous a permis de créer des événements en direct.
1. Vérifiez auprès de votre administrateur que vous disposez d’une licence Teams valide qui autorise la création d’événements en direct.

### <a name="make-sure-viewers-have-permission-to-watch-the-event"></a>Assurez-vous que les téléspectateurs ont l’autorisation de regarder l’événement

Les événements en direct Microsoft Teams ont plusieurs rôles différents pour les autorisations sur l’événement lui-même (Organisateur, Producteur, Présentateur, Participant).

Pour plus d’informations, consultez Rôles de groupe d’événements [Microsoft Teams](https://support.office.com/article/microsoft-teams-live-events-overview-d077fec2-a058-483e-9ab5-1494afda578a#bkmk_roles) .

## <a name="producing-a-live-event"></a>Production d’un événement en direct

### <a name="i-dont-know-how-to-set-up-my-encoder"></a>Je ne sais pas comment configurer mon encodeur

Le moyen le plus simple de commencer consiste à suivre les instructions décrites dans l’article [Utilisation d’un encodeur pour la diffusion en continu en direct dans Microsoft Teams](teams-encoder-setup.md) .

### <a name="my-encoder-isnt-connecting-to-the-server-ingest-url"></a>Mon encodeur ne se connecte pas à l’URL d’ingestion du serveur

- Vérifiez que l’URL RTMP est correctement entrée comme sortie de votre encodeur.
- Vérifiez que la clé RTMP est correctement entrée comme sortie de votre encodeur.
- Vérifiez l’état de votre connexion Internet pour vous assurer que votre encodeur est correctement connecté et en ligne.
- Vous pouvez avoir des paramètres liés à la sécurité réseau ou au pare-feu qui peuvent bloquer la sortie de votre connexion.
- Votre encodeur n’est peut-être pas pris en charge avec Teams. Consultez la liste des encodeurs testés dans [Utilisation d’un encodeur pour le streaming en direct dans Microsoft Teams](teams-encoder-setup.md).

### <a name="i-cant-get-rtmps-to-work"></a>Je ne parviens pas à faire fonctionner les RTPM

- Certains encodeurs peuvent prendre en charge une implémentation différente qui n’est pas prise en charge par Teams. Consultez la liste des encodeurs testés qui fonctionnent avec Teams dans [Utilisation d’un encodeur pour le streaming en direct dans Microsoft Teams](teams-encoder-setup.md).
- Tous les encodeurs ou versions ne prennent pas en charge les rtmp. Contactez le fabricant ou le créateur du logiciel pour voir ce qu’ils prennent en charge.

### <a name="i-tried-to-start-setup-and-its-taking-a-long-time"></a>J’ai essayé de démarrer la configuration et cela prend beaucoup de temps

En général, la configuration peut prendre quelques minutes avant de commencer à envoyer (push) votre encodeur. Il est possible que si le service est occupé que cela prenne plus de temps pour démarrer, il est donc recommandé de vous donner suffisamment de temps pour démarrer la configuration avant votre événement en direct planifié.

### <a name="i-tried-to-start-setup-but-there-are-too-many-events-happening"></a>J’ai essayé de démarrer l’installation, mais il y a trop d’événements qui se produisent

Si vous recevez un message lors du démarrage d’un événement indiquant que le nombre maximal d’événements a été atteint, contactez un administrateur Teams, qui a la possibilité d’arrêter d’autres événements afin de libérer de l’espace pour un événement de priorité plus élevée.

### <a name="i-cant-see-producer-view"></a>Je ne vois pas la vue du producteur

1. L’affichage de l’aperçu du producteur peut prendre quelques secondes une fois que vous avez commencé la diffusion en continu à partir de votre encodeur.
1. Assurez-vous que l’encodeur est connecté à Teams.
1. Il peut parfois être utile d’actualiser la page dans Teams. Vous serez peut-être invité à quitter la page. cela n’affectera pas votre événement en direct.
1. Certains réseaux peuvent bloquer l’accès au contenu. Vérifiez que vos paramètres de sécurité réseau et de pare-feu autorisent le protocole RTMP et que les [domaines requis](/microsoft-365/enterprise/urls-and-ip-address-ranges) figurent dans la liste autorisée. Il peut être utile d’essayer de voir s’il fonctionne sur un autre environnement réseau, indépendant d’un réseau d’entreprise, d’un VPN ou d’un réseau verrouillé.

### <a name="my-feed-looks-bad-has-poor-quality-or-is-glitchy"></a>Mon aliment a l’air mauvais, a une mauvaise qualité, ou est un problème

1. Vérifiez la bande passante de chargement à partir de la machine à partir de laquelle vous envoyez le flux en direct. Une bande passante faible peut entraîner des chutes d’images, une mauvaise qualité ou un flux vidéo à la recherche d’un problème. Vous avez besoin d’une bande passante de chargement supérieure à la vitesse de transmission à laquelle vous diffusez en continu.
1. Vérifiez que vous utilisez les paramètres d’encodeur recommandés pour Teams. Pour plus d’informations, consultez [Configurer manuellement des encodeurs pour le streaming d’événements en direct dans Microsoft Teams](teams-encoder-configuration.md) .
1. Vérifiez que l’audio/vidéo entrant dans l’encodeur n’a aucun problème. Les flux audio ou vidéo sources acheminés vers l’encodeur peuvent avoir eux-mêmes des problèmes, ce qui entraînerait une mauvaise expérience envoyée aux utilisateurs.
1. Vérifiez la charge du processeur sur votre encodeur. Il se peut que vous maxingez votre processeur avec le contenu source et/ou avec la vitesse de transmission que vous essayez d’envoyer (push). Si la charge processeur est trop élevée, essayez de réduire la complexité de vos superpositions/contenu de flux en direct ou réduisez le débit binaire auquel vous diffusez en continu.
1. Vérifiez que votre encodeur est à jour. S’il s’agit d’un encodeur matériel, vérifiez que vous disposez des dernières mises à jour du microprogramme. S’il s’agit d’un encodeur logiciel, vérifiez que vous exécutez la dernière version.
1. Essayez de réinitialiser ou de redémarrer votre encodeur. Notez que si vous effectuez cette opération pendant un flux en direct, vos visionneuses verront une erreur pendant la lecture pendant le redémarrage de votre encodeur. Après avoir redémarré le streaming en direct à partir de l’encodeur, les visionneuses devront recharger la page pour obtenir à nouveau le flux en direct.

### <a name="i-ended-my-live-event-from-my-encoder-but-viewers-are-seeing-an-error"></a>J’ai mis fin à mon événement en direct à partir de mon encodeur, mais les téléspectateurs voient une erreur

Sélectionnez **Arrêter l’événement** avant de déconnecter votre encodeur. Si vous avez déjà déconnecté votre encodeur, vous pouvez toujours sélectionner **Arrêter l’événement**, mais les visionneuses peuvent voir une erreur.

### <a name="my-viewers-are-seeing-issues"></a>Mes téléspectateurs voient des problèmes

- Si une seule visionneuse signale un problème, assurez-vous que la visionneuse dispose d’une bande passante suffisante et qu’elle dispose d’une bonne connexion Internet pour regarder l’événement.
- Si plusieurs personnes au sein d’un même réseau rencontrent des problèmes, il se peut que vous rencontriez des problèmes liés à la congestion du réseau. Passez [en revue la mise à l’échelle de la distribution vidéo et surveillez le trafic réseau à l’aide d’eCDN avec Microsoft Teams](teams-stream-ecdn.md) pour voir si vous pouvez identifier une solution à votre problème.
- Souvent, lorsque plusieurs visionneuses voient un problème, il est en fait lié au flux d’encodeur.
  - Vérifiez que l’encodeur est correctement défini sur les spécifications décrites dans la configuration de l’encodeur et correctement configurée.
  - Vérifiez que vous disposez de suffisamment de bande passante de chargement pour le streaming. Vous pouvez essayer de réduire la bande passante à partir de la sortie de l’encodeur.
  - Parfois, la réinitialisation de l’encodeur aide, mais notez que vous devez conserver les mêmes paramètres lors de la reconnexion. Les membres de l’audience peuvent voir une erreur ou un problème dans l’événement en direct.

### <a name="i-or-my-viewers-cant-hear-the-video"></a>Je, ou mes téléspectateurs, ne peuvent pas entendre la vidéo

1. Vérifiez que l’encodeur envoie du contenu audio.
1. Vérifiez que le périphérique audio est branché.
1. Si vous êtes sur Windows, vérifiez que le périphérique audio approprié est sélectionné et désactivé.
1. En cas d’interruption de l’encodeur, certains navigateurs ou appareils peuvent ne pas être en mesure de récupérer et de lire l’audio correctement.

> [!NOTE]
> Si vous avez déployé Microsoft eCDN en tant que fournisseur de distribution vidéo pour les événements en direct, consultez [Résolution des problèmes de performances eCDN](/ecdn/troubleshooting/troubleshoot-ecdn-performance-issues) pour plus d’informations sur la résolution des problèmes de performances eCDN que vous pouvez rencontrer.
