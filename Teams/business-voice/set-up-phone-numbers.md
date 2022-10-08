---
title: Configurer Téléphonie Microsoft Teams Système avec des numéros de téléphone du plan d’appel
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment configurer Téléphonie Microsoft Teams Système avec des numéros de téléphone forfait d’appels pour les utilisateurs et les services de votre organisation.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
- M365initiative-voice
ms.openlocfilehash: 9052fc0902c069e1ef097810a58f4adcbbae6174
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480864"
---
# <a name="step-2-set-up-teams-phone-system-phone-numbers"></a>Étape 2 : Configurer les numéros de téléphone du système téléphonique Teams

Avant de pouvoir configurer des utilisateurs ou des standards automatiques dans votre organisation, vous devez obtenir des numéros de téléphone pour eux. Il existe plusieurs types de numéros de téléphone différents, mais voici les deux types de numéros que vous devez ajouter à cette étape :

- **Numéros de service** Ces numéros sont utilisés pour les standards automatiques, les audioconférences et les files d’attente d’appels. Il peut s’agir de numéros payants ou gratuits et peuvent gérer de grandes quantités d’appels en même temps. Votre numéro de téléphone d’entreprise doit être un numéro de service, car il sera affecté à un standard automatique dans une étape ultérieure.
- **Numéros d’abonné** Ces numéros sont utilisés pour les utilisateurs réguliers afin qu’ils puissent passer et recevoir des appels téléphoniques.

> [!IMPORTANT]
> Même si vous souhaitez utiliser vos numéros de téléphone existants, vous devez créer et affecter des numéros de téléphone temporaires à la ligne téléphonique principale de votre entreprise et à vos utilisateurs. Vous pourrez remplacer ces numéros temporaires par vos numéros de téléphone existants dans une étape ultérieure.

> [!NOTE]
> La disponibilité de vos nouveaux numéros de téléphone dans Teams peut prendre plusieurs heures.

## <a name="set-up-a-service-number"></a>Configurer un numéro de service

Le numéro de service que vous configurez maintenant sera utilisé ultérieurement pour le numéro de téléphone principal de votre entreprise.

1. Ouvrez le Centre d’administration Microsoft Teams et connectez-vous avec un utilisateur administrateur général (il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365).
2. Dans le volet de navigation gauche, accédez aux <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**numéros de téléphone** **vocal** > </a>, puis cliquez sur **Ajouter**.
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, procédez comme suit :
    1. Sous **Pays ou région**, sélectionnez un pays ou une région.
    2. Sous **Type de nombre**, sélectionnez l’une des options suivantes :

        - **Standard automatique (numéro)** Numéro de téléphone standard, non payant. Les frais de longue distance sont facturés à l’appelant.
        - **Standard automatique (gratuit)** Numéro de téléphone gratuit (États-Unis et Canada) ou gratuit (Royaume-Uni). Les frais de longue distance sont facturés à votre entreprise. Avant de pouvoir sélectionner cette option, vous devez acheter des crédits de communication. Pour plus d’informations, consultez [Ce que j’ai besoin d’acheter pour obtenir des fonctionnalités vocales pour ma petite ou moyenne entreprise?](whats-business-voice.md).

    3. Sous **Quantité**, sélectionnez **1**.
        > [!NOTE]
        > Si vous recevez le message **Vous n’avez pas suffisamment de licences pour demander d’autres numéros de ce type**, assurez-vous que vous avez acheté des licences De téléphone Teams avec forfait d’appels groupés. Pour plus d’informations, consultez [Ce que j’ai besoin d’acheter pour obtenir des fonctionnalités vocales pour ma petite ou moyenne entreprise?](whats-business-voice.md).
    4. Choisissez **l’emplacement** ou **le code de zone**, selon que vous souhaitez rechercher des numéros de téléphone à l’aide de la ville d’un emplacement ou si vous souhaitez rechercher des numéros dans un code régional spécifique.
    5. Si vous sélectionnez **Emplacement** :

        1. Tapez la ville dans laquelle se trouve votre adresse d’urgence à l’étape [Configurer les emplacements d’urgence](set-up-emergency-locations.md) , ou si vous devez créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur **Ajouter un emplacement**.
        2. Sous **Code de** zone, sélectionnez un code de zone, puis sélectionnez **Suivant** pour réserver votre numéro.

    6. Si vous sélectionnez **Code de** zone, tapez le code de zone à rechercher, puis sélectionnez **Suivant** pour réserver votre numéro.

5. Sélectionnez le nombre souhaité. Vous avez 10 minutes pour sélectionner votre numéro de téléphone et passer votre commande. Si vous prenez plus de 10 minutes, le numéro de téléphone est renvoyé au pool de numéros.
6. Lorsque vous êtes prêt à passer votre commande, cliquez sur **Passer la commande**, puis **terminez**

## <a name="set-up-phone-numbers-for-your-users"></a>Configurer des numéros de téléphone pour vos utilisateurs

1. Ouvrez le Centre d’administration Microsoft Teams et connectez-vous avec un utilisateur administrateur général. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
2. Dans le volet de navigation gauche, accédez aux <a href="https://admin.teams.microsoft.com/phone-numbers" target="_blank">**numéros de téléphone** **vocal** > </a>, puis cliquez sur **Ajouter**.
3. Entrez un nom pour la commande et ajoutez une description.
4. Dans la page Emplacement et quantité, procédez comme suit :

    1. Sous **Pays ou région**, sélectionnez un pays ou une région.
    2. Sous **Type de numéro**, sélectionnez **Utilisateur (abonné).**
    3. Sous **Quantité**, entrez le nombre de numéros souhaités pour votre organisation.
    4. Choisissez **l’emplacement** ou **le code de zone**, selon que vous souhaitez rechercher des numéros de téléphone à l’aide de la ville d’un emplacement ou si vous souhaitez rechercher des numéros dans un code régional spécifique.
    5. Si vous sélectionnez **Emplacement** :

        1. Tapez la ville dans laquelle se trouve votre adresse d’urgence à l’étape [Configurer les emplacements d’urgence](set-up-emergency-locations.md) , ou si vous devez créer un nouvel emplacement pour un autre bureau ou un bureau à domicile, cliquez sur **Ajouter un emplacement**.
        2. Sous **Code de** zone, sélectionnez un code de zone, puis sélectionnez **Suivant** pour réserver votre numéro.

    6. Si vous sélectionnez **Code de** zone, tapez le code de zone à rechercher, puis sélectionnez **Suivant** pour réserver votre numéro.
5. Sélectionnez les nombres souhaités. Vous avez 10 minutes pour sélectionner vos numéros de téléphone et passer votre commande. Si vous prenez plus de 10 minutes, les numéros de téléphone sont renvoyés au pool de numéros.
6. Lorsque vous êtes prêt à passer votre commande, cliquez sur **Passer la commande**, puis **terminez**.

> [!div class="nextstepaction"]
> [Étape suivante : Attribuer des licences aux utilisateurs Teams](set-up-licenses.md)
