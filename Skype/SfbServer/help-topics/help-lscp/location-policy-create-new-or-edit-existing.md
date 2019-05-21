---
title: Stratégie d’emplacement création d’un nouveau ou modification existante
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: b0b1e16f7227100394dd132e52a17a3192ccab43
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293500"
---
# <a name="location-policy-create-new-or-edit-existing"></a>Stratégie d’emplacement : création d’une stratégie ou modification d’une stratégie existante

Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.

- **Scope** Identifie l’étendue de la stratégie d’emplacement que vous créez ou modifiez: global, site ou utilisateur.

- **Nom** Chaque stratégie d’emplacement nécessite un nom. Les stratégies d’emplacement global et de site sont nommées par défaut et le nom ne peut pas être modifié. Pour les stratégies d’emplacement des utilisateurs, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.

    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie d’emplacement, vous ne pouvez plus modifier son nom.

- **Activer les 9-1-1 améliorés (E9-1-1)** Activez cette case à cocher pour activer E9-1-1 pour les utilisateurs auxquels cette stratégie d’emplacement est affectée.

- **Emplacement** Spécifiez si les utilisateurs sont invités à entrer des informations d’emplacement:

  - **Obligatoire** Sélectionnez cette option si les utilisateurs doivent être invités à entrer des informations d’emplacement lorsque leur client s’inscrit à un nouvel emplacement. Les utilisateurs peuvent ignorer l’invite sans entrer d’informations d’emplacement.

  - **Facultatif** Sélectionnez cette option si les utilisateurs ne doivent pas être invités à entrer des informations d’emplacement.

  - **Exclusion de responsabilité** Sélectionnez cette option si les utilisateurs doivent être invités à entrer des informations d’emplacement, mais ils verront s’afficher un message d’exclusion de responsabilité s’ils refusent l’invite sans entrer les informations. Les utilisateurs peuvent effectuer un appel d’urgence sans passer d’autres appels tant qu’ils n’ont pas entré les informations d’emplacement.

- **Utiliser l’emplacement pour E9-1-1 uniquement** Activez cette case à cocher si les informations d’emplacement doivent uniquement être utilisées pour les appels d’urgence.

- **Utilisation PSTN** Sélectionnez l’utilisation de réseau téléphonique commuté (PSTN) qui sera utilisée pour déterminer le numéro de téléphone à utiliser pour diriger les appels d’urgence à partir de clients qui utilisent ce profil. L’itinéraire associé à cette utilisation doit pointer vers un Trunk SIP dédié aux appels d’urgence ou à une passerelle ELIN (Emergency Identification Number) qui route les appels d’urgence vers le point de réponse de sécurité publique le plus proche (PSAPI). Les options sont **Internal**, **local**ou **longue distance**.

- **E9-1-1 Numéro de** téléphone Spécifiez le numéro numéroté pour contacter les services d’urgence.

- **E9-1-1 masque de numérotation** Spécifiez le numéro de téléphone d’un utilisateur, qui est ensuite traduit par le numéro de téléphone d’urgence. Par exemple, entrez une valeur de 212 dans ce champ pour permettre à un utilisateur de composer 212 afin d’accéder aux services d’urgence. Cela permet d’appeler d’autres numéros d’urgence et de toujours avoir accès aux services d’urgence (par exemple, si un membre d’un pays ou d’une région dont le numéro de téléphone est différent pour composer le numéro de votre pays ou de votre région, et non le numéro de la pays ou région dans lequel ils se trouvent actuellement). Vous pouvez définir plusieurs masques de numérotation d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212; 414. La longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre compris entre 0 et 9.

    > [!IMPORTANT]
    > Assurez-vous que le masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués, car l’acheminement du parcage d’appels est prioritaire sur la conversion des chaînes d’appel d’urgence. Pour afficher les plages de numéros des appels, cliquez sur **fonctionnalités vocales** dans la barre de navigation gauche, puis cliquez sur **parc d’appels**.

- **URI de notification** Spécifiez un ou plusieurs URI SIP à avertir en cas d’appel d’urgence. Par exemple, tapez l’URI SIP de l’entreprise de sécurité d’entreprise pour notifier l’équipe de sécurité avec un message instantané dès qu’un appel d’urgence est effectué. Si l’emplacement de l’appelant est disponible, l’emplacement est inclus dans la notification. Vous pouvez spécifier plusieurs URI SIP en tant que liste séparée par des virgules. Par exemple, «SIP: security@litwareinc.com», «SIP: kmyer@litwareinc.com». La chaîne doit contenir entre 1 et 256 caractères et doit commencer par le préfixe «SIP:». Vous pouvez également spécifier des listes de distribution.

- **URI** de la Conférence Spécifiez l’URI SIP (numéro de téléphone, dans le cas présent), pour qu’un tiers soit reversé aux appels d’urgence. Par exemple, tapez le numéro de téléphone de l’entreprise de sécurité du Bureau pour recevoir un appel en cas d’appel d’urgence. Le paramètre pour le **mode conférence** détermine si le tiers peut participer ou simplement écouter l’appel. La chaîne doit avoir entre 1 et 256 caractères de longueur et doit commencer par le préfixe SIP:.

- **Mode conférence** Si vous avez spécifié une valeur pour **URI de conférence**, définissez ce champ sur l’une des valeurs suivantes:

  - **** Unidirectionnel Spécifie que le tiers peut uniquement écouter l’appel entre l’appelant et l’opérateur PSAPI.

  - **** Bidirectionnel Spécifie que le tiers peut participer à l’appel entre l’appelant et l’opérateur PSAPI.

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du service d’urgence entreprise voix entreprise, voir [vue d’ensemble de E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies d’emplacement, reportez-vous à la rubrique [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) de la documentation des opérations.


