---
title: Configurer les numéros Microsoft 365 Business voix
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer des numéros Microsoft 365 Business voix pour les utilisateurs et les services de votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cec0bc8e55ef6be169de1f48a375ab40ca8ccf7
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130053"
---
# <a name="step-2-set-up-business-voice-phone-numbers"></a>Étape 2 : configurer les numéros de téléphone d'entreprise

Avant de pouvoir configurer des utilisateurs ou des attendants automatiques dans votre organisation, vous devez obtenir des numéros de téléphone pour eux. Il existe plusieurs types de numéros de téléphone. Toutefois, voici les deux types de numéros que vous devez ajouter à cette étape :

- **Numéros de service** Ces numéros sont utilisés pour le support automatique, l'audioconférence et les files d'attente. Ils peuvent être des numéros gratuits ou gratuits et peuvent gérer de grandes quantités d'appels en même temps. Le numéro de téléphone de votre entreprise doit être un numéro de service, car il sera affecté à un agent automatique dans une étape ultérieure.
- **Numéros d'abonné** Ces numéros sont utilisés pour les utilisateurs réguliers afin qu'ils peuvent effectuer et recevoir des appels téléphoniques.

> [!IMPORTANT]
> Même si vous voulez utiliser vos numéros de téléphone existants, vous devez créer et attribuer des numéros de téléphone temporaires à la ligne de téléphone principale de votre entreprise et à vos utilisateurs. Vous pourrez remplacer ces numéros temporaires par vos numéros de téléphone existants dans une étape ultérieure.

> [!NOTE]
> Plusieurs heures peuvent être avant que vos nouveaux numéros de téléphone deviennent disponibles dans Teams.

## <a name="set-up-a-service-number"></a>Configurer un numéro de service

Le numéro de service que vous définissez maintenant sera utilisé dans une étape ultérieure pour le numéro de téléphone principal de votre société.

1. Allez dans le Microsoft Teams d'administration.
2. Dans le groupe de navigation de gauche, cliquez  >  **sur Numéros Téléphone la** voix, puis cliquez sur **Ajouter.**
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, vous pouvez :
    1. Sous **Pays ou région,** sélectionnez un pays ou une région.
    2. Sous **Type de nombre,** sélectionnez l'une des options suivantes :

        - **Service de service automatique (numéro de frais)** Numéro de téléphone normal, non gratuit. Des frais de longue distance sont facturés à l'appelant.
        - **Attendant automatique (numéro gratuit)** Numéro de téléphone gratuit (États-Unis et Canada) ou téléphone gratuit (Royaume-Uni). Les frais d'longue distance sont facturés à votre entreprise. Pour pouvoir sélectionner cette option, vous devez acheter des crédits de communication. Pour plus d'informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?

    3. Sous **Quantité,** sélectionnez **1.**
        > [!NOTE]
        > Si vous recevez un message vous **n'avez** pas assez de licences pour demander davantage de licences de ce type, assurez-vous que vous avez acheté des licences Business Voice. Pour plus d'informations, [voir Que dois-je](what-to-buy.md)acheter pour utiliser Microsoft 365 Business Voice ?
    4. Sous **Emplacement,** tapez le nom de l'emplacement que vous avez créé à l'étape [Configurer les emplacements d'urgence.](set-up-emergency-locations.md)
    5. Sous **Code de la** zone, sélectionnez un code de zone, puis cliquez sur **Suivant** pour sélectionner vos numéros
5. Sélectionnez le nombre de votre choix. Vous avez 10 minutes pour sélectionner votre numéro de téléphone et y placer votre commande. Si cela prend plus de 10 minutes, le numéro de téléphone est renvoyé dans la réserve de numéros.
6. Lorsque vous êtes prêt à passer votre commande, **cliquez** sur Passer commande, puis **terminez**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurer des numéros de téléphone pour vos utilisateurs

1. Allez dans le Microsoft Teams d'administration.
2. Dans le groupe de navigation de gauche, cliquez  >  **sur Numéros Téléphone la** voix, puis cliquez sur **Ajouter.**
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, vous pouvez :

    1. Sous **Pays ou région,** sélectionnez un pays ou une région.
    2. Sous **Type de numéro,** **sélectionnez Utilisateur (abonné).**
    3. Sous **Quantité,** entrez le nombre de nombres que vous souhaitez pour votre organisation.
    4. Sous **Emplacement,** sélectionnez un emplacement. Vous pouvez sélectionner l'emplacement d'urgence que vous avez ajouté à l'étape Configurer les emplacements d'urgence ou, si vous avez besoin de créer un emplacement pour un autre bureau ou un bureau à domicile, cliquer sur Ajouter un **emplacement.** [](set-up-emergency-locations.md)
    5. Sous **Code de la** zone, sélectionnez un code de zone, puis cliquez sur **Suivant** pour sélectionner vos numéros.
5. Sélectionnez les nombres de votre choix. Vous avez 10 minutes pour sélectionner vos numéros de téléphone et placer votre commande. Si cela prend plus de 10 minutes, les numéros de téléphone sont renvoyés dans la réserve de numéros.
6. Lorsque vous êtes prêt à passer votre commande, cliquez **sur** Passer commande, puis sur **Terminer.**

> [!div class="nextstepaction"]
> [Étape suivante : attribuer des licences à Teams utilisateurs](set-up-licenses.md)
