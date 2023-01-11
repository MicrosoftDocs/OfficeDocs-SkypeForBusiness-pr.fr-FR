---
title: Création d’un flux dans Microsoft Teams
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
description: Cet article décrit la création d’un flux pour les événements de streaming Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767950"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Créer un événement en direct dans Microsoft Teams

> [!IMPORTANT]
> **Chine** : actuellement, les utilisateurs situés en Chine ne pourront pas configurer ou participer à des événements en direct Microsoft Teams ou Yammer, ni regarder des vidéos à la demande sans l’aide de leur administrateur informatique.
>
> Avant de commencer, contactez votre administrateur pour voir s’il doit configurer un VPN pour connecter votre réseau d’entreprise afin que ces applications puissent fonctionner en toute transparence dans votre organisation.

> [!IMPORTANT]
> Lors de la configuration d’un événement en direct, nous vous recommandons de configurer vos autorisations vidéo, communauté et utilisateur au moins 24 heures avant l’événement pour une expérience optimale. Cela inclut des paramètres tels que l’ajout d’utilisateurs, la mise à jour des autorisations vidéo et la modification d’une communauté de privé à public. La propagation de certaines modifications sur Microsoft Stream, Microsoft Teams et Microsoft Yammer peut prendre jusqu’à deux (2) heures. L’autorisation de 24 heures ou plus peut fournir du temps pour les tests et apporter des ajustements si nécessaire.

## <a name="schedule-the-live-event"></a>Planifier l’événement en direct

1. Ouvrez le client Microsoft Teams et accédez au calendrier.
1. Utilisez la liste déroulante **Nouvelle réunion** .
1. Sélectionnez l’option **Événement en direct** .
1. Dans la fenêtre contextuelle **Nouvel événement en direct** , entrez les détails de votre événement à gauche (**Titre**, **Emplacement**, **Début**, **Fin**, **Fuseau** horaire et **Détails**).
1. Sur la même page, à droite, **invitez les présentateurs** à ajouter des présentateurs et des producteurs, individuellement ou par le biais de groupes.
1. Lorsque tout est entré, sélectionnez **Suivant**.
1. Sélectionnez **Personnes et groupes**, à **l’échelle de l’organisation** ou **Public** sous **Autorisations d’événement en** direct pour spécifier qui peut regarder l’événement en direct.
1. Sélectionnez **Encodeur Teams (préversion)** sous **Comment allez-vous produire votre événement en direct** ?
1. Configurez les options requises telles que **Q&R**, **Légendes** et autres sous **Options d’événement**.
1. Sélectionnez **Planifier** pour terminer la planification de votre événement en direct.

## <a name="stream-the-live-event"></a>Diffuser l’événement en direct

1. Une fois que vous avez planifié votre événement en direct, vous pouvez récupérer **l’URL d’ingestion du serveur RTMP** et la **clé RTMP** sous la section **DÉTAILS RTMP** de l’invitation de calendrier, que vous pouvez utiliser pour envoyer (push) le contenu de l’encodeur via l’ingestion RTMP.
1. Pour configurer votre encodeur, copiez l’URL d’ingestion RTMP et la clé RTMP dans votre encodeur pour commencer à envoyer le flux d’encodeur dynamique à Team. L’utilisation d’un encodeur pour le streaming en direct dans Microsoft Teams contient plus d’informations.
1. À l’aide d’un client Microsoft Teams, rejoignez l’événement en direct en tant que producteur. Vous pouvez également trouver RTMP Dans les détails dans plus d’options -> Réunion.
1. Lorsque vous commencez à envoyer du contenu de l’encodeur au point d’ingestion du serveur, vous devez voir la mise à jour de la préversion du producteur.
1. Une fois que vous êtes satisfait de votre configuration et que vous pouvez voir l’aperçu dans l’interface utilisateur du producteur, sélectionnez le **flux RTMP** à partir des sources et **Envoyer en direct**.
1. Sélectionnez **Démarrer l’événement** pour démarrer l’événement en direct et publier les membres du public qui peuvent voir l’événement.
1. Lorsque vous avez terminé votre événement, sélectionnez **Terminer l’événement** dans l’interface utilisateur du producteur. Cela met fin à l’événement et rend le contenu immédiatement disponible pour la vidéo à la demande.

Pour plus d’informations sur la diffusion en continu de l’événement en direct, consultez [Produire un événement en direct à l’aide de l’encodeur Teams](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9).
