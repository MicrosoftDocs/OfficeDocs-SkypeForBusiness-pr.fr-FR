---
title: 'Stratégie d’emplacement : création d’une stratégie d’emplacement ou modification d’une stratégie existante'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: Vous pouvez configurer des stratégies d’emplacement pour déterminer si Enhanced 9-1-1 (E9-1-1) est activé et comment il est utilisé, ainsi que la façon dont les informations d’emplacement sont utilisées pour les utilisateurs et les contacts.
ms.openlocfilehash: 8f45fefbd13d20e5bdbef2500b17a394f544aad1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764642"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Stratégie d’emplacement : création d’une nouvelle ou modification d’une stratégie existante

Vous pouvez configurer des stratégies d’emplacement pour déterminer si Enhanced 9-1-1 (E9-1-1) est activé et comment il est utilisé, ainsi que la façon dont les informations d’emplacement sont utilisées pour les utilisateurs et les contacts.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les champs de la page.

- **Étendue** Identifie l’étendue de la stratégie d’emplacement que vous créez ou modifiez : global, site ou utilisateur.

- **Nom** Chaque stratégie d’emplacement nécessite un nom. Les stratégies globales et d’emplacement de site sont nommées par défaut et le nom ne peut pas être modifié. Pour les stratégies d’emplacement utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie d’emplacement, son nom ne peut plus être modifié.

- **Activer Enhanced 9-1-1 (E9-1-1)** Activez cette case à cocher pour activer E9-1-1 pour les utilisateurs affectés à cette stratégie d’emplacement.

- **Emplacement** Spécifiez si les utilisateurs sont invités à fournir des informations d’emplacement :

  - **Obligatoire** Sélectionnez cette option si les utilisateurs doivent être invités à fournir des informations d’emplacement lorsque leur client s’inscrit à un nouvel emplacement. Les utilisateurs peuvent ignorer l’invite sans entrer d’informations d’emplacement.

  - **Non requis** Sélectionnez cette option si les utilisateurs ne doivent pas être invités à fournir des informations d’emplacement.

  - **Clause d’exclusion de responsabilité** Sélectionnez cette option si les utilisateurs doivent être invités à entrer des informations d’emplacement, mais un message de clause d’exclusion de responsabilité s’ils refusent l’invite sans entrer les informations s’y trouve. Les utilisateurs peuvent effectuer un appel d’urgence, mais aucun autre appel tant qu’ils n’ont pas entré les informations d’emplacement.

- **Utiliser l’emplacement pour E9-1-1 uniquement** Cochez cette case si les informations d’emplacement doivent être utilisées uniquement pour les appels d’urgence.

- **Utilisation PSTN** Sélectionnez l’utilisation du réseau téléphonique commuté (PSTN) qui sera utilisée pour déterminer l’itinéraire de communications vocales qui sera utilisé pour le routage des appels d’urgence des clients qui utilisent ce profil. L’itinéraire associé à cette utilisation doit pointer sur une jonction SIP dédiée aux appels d’urgence ou à une passerelle ELIN (Emergency Location Identification Number) qui route les appels d’urgence vers le centre téléphonique de sécurité publique (Public Safety Answering Point ou PSAP) le plus proche. Les options **sont Interne,** **Local** ou **Longue distance.**

- **Numéro de numéro de numérotation E9-1-1** Spécifiez le numéro composé pour joindre les services d’urgence.

- **Masque de numérotation E9-1-1** Spécifiez un numéro qu’un utilisateur compose, qui est ensuite converti en numéro de numéro d’urgence. Par exemple, entrez la valeur 212 dans ce champ pour qu’un utilisateur puisse composer le 212 pour joindre les services d’urgence. Cela permet de composer d’autres numéros d’urgence tout en permettant à l’appel d’atteindre les services d’urgence (par exemple, si une personne d’un pays ou d’une région avec un numéro d’urgence différent tente de composer le numéro de ce pays ou de cette région plutôt que le numéro du pays ou de la région où elle se trouve actuellement). Vous pouvez définir plusieurs masques d’appel d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212;414. La longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.

    > [!IMPORTANT]
    > Assurez-vous que le masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués, car le routage du parcage d’appels est prioritaire sur la conversion des chaînes d’appel d’urgence. Pour voir les plages de  numéro de parcier d’appel, cliquez sur Fonctionnalités vocales dans la barre de navigation de gauche, puis cliquez sur Parcer **l’appel.**

- **URI de notification** Spécifiez un ou plusieurs URIs SIP à notifiant lorsqu’un appel d’urgence est effectué. Par exemple, tapez l’URI SIP du bureau de sécurité de l’entreprise pour avertir le personnel de sécurité par un message instantané chaque fois qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant est disponible, il est inclus dans la notification. Vous pouvez spécifier plusieurs URS SIP en tant que liste séparée par des virgules. Par exemple, « sip:security@litwareinc.com »,« sip:kmyer@litwareinc.com ». La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe « sip: ». Vous pouvez également spécifier des listes de distribution.

- **URI de conférence** Spécifiez l’URI SIP (numéro de téléphone, dans ce cas) pour qu’un tiers soit téléconférence aux appels d’urgence. Par exemple, tapez le numéro de téléphone du service de sécurité de la société afin qu’il reçoie un appel lorsqu’un appel d’urgence est effectué. Le paramètre du **mode Conférence** détermine si le tiers peut participer ou simplement écouter l’appel. La chaîne doit comporter entre 1 et 256 caractères et commencer par le préfixe sip:.

- **Mode conférence** Si vous avez spécifié une valeur pour **l’URI** de conférence, définissez ce champ sur l’une des valeurs suivantes :

  - **À sens seul** Spécifie que le tiers peut uniquement écouter l’appel entre l’appelant et l’opérateur psap.

  - **Deux voies** Spécifie que le tiers peut participer à l’appel entre l’appelant et l’opérateur DUP.

Pour plus d’informations Voix Entreprise fonctionnalités des services d’urgence, voir Vue d’ensemble du [service E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) dans la documentation des opérations.