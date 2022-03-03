---
title: Configurer des numéros Microsoft Teams Système téléphonique des forfaits d’appels
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: Découvrez comment configurer des appels Microsoft Teams Système téléphonique des numéros de téléphone de plan d’appels pour les utilisateurs et les services de votre organisation.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19d2b165e85620b0fb9e9e8242adacc4c07f2c53
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053253"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Étape 2 : configurer Teams Système téléphonique numéros de téléphone

Avant de pouvoir configurer des utilisateurs ou des attendants automatiques dans votre organisation, vous devez obtenir des numéros de téléphone pour eux. Il existe plusieurs types de numéros de téléphone. Toutefois, voici les deux types de numéros que vous devez ajouter à cette étape :

- **Numéros de service** Ces numéros sont utilisés pour le support automatique, l’audioconférence et les files d’attente. Ils peuvent être des numéros gratuits ou gratuits et peuvent gérer de grandes quantités d’appels en même temps. Le numéro de téléphone de votre entreprise doit être un numéro de service, car il sera affecté à un agent automatique dans une étape ultérieure.
- **Numéros d’abonné** Ces numéros sont utilisés pour les utilisateurs réguliers, de sorte qu’ils peuvent effectuer et recevoir des appels téléphoniques.

> [!IMPORTANT]
> Même si vous voulez utiliser vos numéros de téléphone existants, vous devez créer et attribuer des numéros de téléphone temporaires à la ligne de téléphone principale de votre entreprise et à vos utilisateurs. Vous pourrez remplacer ces numéros temporaires par vos numéros de téléphone existants dans une étape ultérieure.

> [!NOTE]
> L’accès à vos nouveaux numéros de téléphone dans Teams peut prendre plusieurs heures.

## <a name="set-up-a-service-number"></a>Configurer un numéro de service

Le numéro de service que vous définissez maintenant sera utilisé dans une étape ultérieure pour le numéro de téléphone principal de votre société.

1. Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).
2. Dans le groupe de navigation de gauche, cliquez sur <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Téléphone** >  **voix**</a>, puis cliquez sur **Ajouter**.
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, vous pouvez :
    1. Sous **Pays ou région**, sélectionnez un pays ou une région.
    2. Sous **Type de nombre**, sélectionnez l’une des options suivantes :

        - **Service de service automatique (numéro de frais)** Numéro de téléphone normal, non gratuit. Des frais de longue distance sont facturés à l’appelant.
        - **Attendant automatique (numéro gratuit)** Numéro de téléphone gratuit (États-Unis et Canada) ou téléphone gratuit (Royaume-Uni). Les frais d’longue distance sont facturés à votre entreprise. Pour pouvoir sélectionner cette option, vous devez acheter des crédits de communication. Pour plus d’informations, voir Que dois-je acheter pour obtenir des [fonctionnalités vocales pour ma petite ou moyenne entreprise](whats-business-voice.md) ?

    3. Sous **Quantité**, sélectionnez **1**.
        > [!NOTE]
        > Si vous obtenez un message vous **n’avez** pas assez de licences pour demander davantage de numéros de ce type, assurez-vous que vous avez acheté des licences Teams Téléphone avec des licences groupées de plan d’appels. Pour plus d’informations, voir Que dois-je acheter pour obtenir des [fonctionnalités vocales pour ma petite ou moyenne entreprise](whats-business-voice.md) ?
    4. Choisissez Emplacement **ou** **Code** de la zone, selon que vous souhaitez rechercher des numéros de téléphone en utilisant la ville d’un lieu ou si vous souhaitez rechercher des numéros dans un code de zone spécifique.
    5. Si vous sélectionnez **Emplacement** :

        1. Tapez la ville dans laquelle se trouve votre adresse de secours à l’étape Configurer les emplacements d’urgence, ou si vous avez besoin de créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur Ajouter un **emplacement**.[](set-up-emergency-locations.md)
        2. Sous **Code de la** zone, sélectionnez un code de zone, puis **sélectionnez Suivant** pour réserver votre numéro.

    6. Si vous sélectionnez **l’code de** la zone, tapez l’code de la zone à rechercher, puis sélectionnez **Suivant** pour réserver votre numéro.

5. Sélectionnez le nombre de votre choix. Vous avez 10 minutes pour sélectionner votre numéro de téléphone et y placer votre commande. Si cela prend plus de 10 minutes, le numéro de téléphone est renvoyé dans la réserve de numéros.
6. Lorsque vous êtes prêt à passer votre commande **, cliquez sur** Passer commande, puis **terminez**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurer des numéros de téléphone pour vos utilisateurs

1. Ouvrez le Microsoft Teams d’administration et connectez-vous avec un utilisateur en tant qu’administrateur global. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
2. Dans le groupe de navigation de gauche, cliquez sur <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**Téléphone** >  **voix**</a>, puis cliquez sur **Ajouter**.
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, vous pouvez :

    1. Sous **Pays ou région**, sélectionnez un pays ou une région.
    2. Sous **Type de nombre**, **sélectionnez Utilisateur (abonné).**
    3. Sous **Quantité**, entrez le nombre de nombres que vous souhaitez pour votre organisation.
    4. Choisissez Emplacement **ou** **Code** de la zone, selon que vous souhaitez rechercher des numéros de téléphone en utilisant la ville d’un lieu ou si vous souhaitez rechercher des numéros dans un code de zone spécifique.
    5. Si vous sélectionnez **Emplacement** :

        1. Tapez la ville dans laquelle se trouve votre adresse de secours à l’étape Configurer les emplacements d’urgence, ou si vous avez besoin de créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur Ajouter un **emplacement**.[](set-up-emergency-locations.md)
        2. Sous **Code de la** zone, sélectionnez un code de zone, puis **sélectionnez Suivant** pour réserver votre numéro.

    6. Si vous sélectionnez **l’code de** la zone, tapez l’code de la zone à rechercher, puis sélectionnez **Suivant** pour réserver votre numéro.
5. Sélectionnez les nombres de votre choix. Vous avez 10 minutes pour sélectionner vos numéros de téléphone et placer votre commande. Si cela prend plus de 10 minutes, les numéros de téléphone sont renvoyés dans la réserve de numéros.
6. Lorsque vous êtes prêt à passer votre commande, cliquez **sur** Passer commande, puis sur **Terminer**.

> [!div class="nextstepaction"]
> [Étape suivante : attribuer des licences à Teams utilisateurs](set-up-licenses.md)
