---
title: Stratégie d’emplacement créer ou modifier une existant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: 836435704ddd27356be2d39fdd278891b2bbfcd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891144"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Stratégie d’emplacement : création d’une stratégie ou modification d’une stratégie existante

Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Étendue** Identifie l’étendue de la stratégie d’emplacement que vous créez ou modifiez : globale, site ou utilisateur.

- **Nom** Chaque stratégie d’emplacement requiert un nom. Stratégies d’emplacement globaux et de site sont nommées par défaut, et le nom ne peut pas être modifié. Pour les stratégies d’emplacement utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou un groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie d’emplacement, vous ne pouvez plus modifier son nom.

- **Activer Enhanced 9-1-1 (E9-1-1)** Activez cette case à cocher pour activer E9-1-1 pour les utilisateurs auxquels cette stratégie d’emplacement.

- **Emplacement** Spécifiez si les utilisateurs sont invités informations d’emplacement :

  - **Requis** Sélectionnez cette option si les utilisateurs doivent fournir des informations d’emplacement lors de leur client s’inscrit à un nouvel emplacement. Les utilisateurs peuvent ignorer l’invite sans saisir les informations d’emplacement.

  - **Non requis** Sélectionnez cette option si les utilisateurs ne doivent ne pas fournir des informations d’emplacement.

  - **Notification d’exclusion** Sélectionnez cette option si les utilisateurs doivent fournir des informations d’emplacement, mais seront affiche un message de notification d’exclusion s’il refuse l’invite sans saisir les informations. Les utilisateurs peuvent effectuer un appel d’urgence, mais aucun autre appel avant d’avoir entré les informations d’emplacement.

- **Utiliser l’emplacement pour E9-1-1 uniquement** Activez cette case à cocher si les informations d’emplacement doit être utilisé uniquement pour les appels d’urgence.

- **Utilisation PSTN** Sélectionnez l’utilisation du réseau (PSTN) public commuté qui sera utilisée pour déterminer quel itinéraire vocal sera utilisé pour acheminer les appels d’urgence à partir de clients qui utilisent ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle d’urgence ELIN Location Identification Number () qui achemine les appels d’urgence pour le plus proche Public Safety Answering pointez (PSAP). Les options sont **interne**, **Local**ou **longue distance**.

- **Numéro d’E9-1-1** Spécifiez le numéro qui est composé pour joindre les services d’urgence.

- **Masque de numérotation E9-1-1** Spécifier qu’un utilisateur compose un numéro, qui est ensuite converti en numéro d’urgence. Par exemple, entrez une valeur de 212 dans ce champ afin qu’un utilisateur peut composer 212 pour joindre les services d’urgence. Ainsi, pour les numéros d’urgence substitution être composé tout en conservant l’appel joindre les services d’urgence (par exemple, si une personne de votre pays ou région avec un autre numéro d’urgence tente de numérotation que le pays ou la région s numérique plutôt que le numéro de la pays ou région dans que se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212 ; 414. La longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre de 0 à 9.

    > [!IMPORTANT]
    > Assurez-vous que le masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués, car l’acheminement du parcage d’appels est prioritaire sur la conversion des chaînes d’appel d’urgence. Pour voir les plages de numéros de parcage d’appel, cliquez sur **Fonctionnalités vocales** dans la barre de navigation de gauche, puis cliquez sur **Mise en garde d’appels**.

- **URI de notification** Spécifiez un ou plusieurs URI SIP à notifier lorsqu’un appel d’urgence est effectué. Par exemple, tapez URI SIP de l’office sécurité société pour notifier le personnel de sécurité avec un message instantané chaque fois qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant n’est disponible, l’emplacement est inclus dans la notification. Vous pouvez spécifier plusieurs URI SIP sous forme de liste séparée par des virgules. Par exemple, « sip:security@litwareinc.com », « sip:kmyer@litwareinc.com ». La chaîne doit être comprise entre 1 et 256 caractères et doit commencer par le préfixe « sip : ». Vous pouvez également spécifier des listes de distribution.

- **URI de conférence** Spécifiez l’URI SIP (numéro de téléphone, dans ce cas) à un tiers à participer à des appels d’urgence. Par exemple, tapez numéro de téléphone du bureau de sécurité de société afin qu’ils reçoivent un appel lors d’un appel d’urgence. Le paramètre de **mode conférence** détermine si le tiers peut participer ou qu’écouter l’appel. La chaîne doit être comprise entre 1 et 256 caractères et doit commencer par le préfixe sip :.

- **Mode conférence** Si vous avez spécifié une valeur pour **URI de la conférence**, définissez ce champ sur une des valeurs suivantes :

  - **À sens unique** Spécifie que le tiers peut uniquement écouter l’appel entre l’appelant et l’opérateur du centre.

  - **Bidirectionnelle** Spécifie que le tiers peut participer à l’appel entre l’appelant et l’opérateur du centre.

Pour plus d’informations sur les fonctionnalités de service d’urgence Enterprise Voice, voir [vue d’ensemble de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, reportez-vous à la rubrique [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) de la documentation des opérations.


