---
title: Stratégie d’emplacement créer ou modifier une existante
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: cc2d5119e4bb21badf96dcf24099844ffffd0639
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy-create-new-or-edit-existing"></a>Stratégie d’emplacement : création d’une stratégie ou modification d’une stratégie existante
 
Vous pouvez configurer les stratégies d’emplacement pour déterminer si le service E9-1-1 (Enhanced 9-1-1) est activé et pour savoir comment il est utilisé et comment les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
  
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les champs de la page.
  
- **Champ d’application** Identifie l’étendue de la stratégie de l’emplacement que vous créez ou modifiez : global, site ou à l’utilisateur.
    
- **Nom** Chaque stratégie d’emplacement requiert un nom. Stratégies d’emplacement globaux et de site sont nommées par défaut, et le nom ne peut pas être modifié. Pour les stratégies d’emplacement utilisateur, utilisez un nom descriptif qui identifie l’utilisateur ou le groupe d’utilisateurs.
    
    > [!NOTE]
    > Une fois que vous avez enregistré la stratégie d’emplacement, vous ne pouvez plus modifier son nom. 
  
- **Activer améliorée 9-1-1 (E9-1-1)** Activez cette case à cocher pour activer le E9-1-1 pour les utilisateurs qui ont cette stratégie d’emplacement.
    
- **Emplacement** Spécifiez si les utilisateurs sont invités à des informations d’emplacement :
    
  - **Requis** Sélectionnez cette option si les utilisateurs doivent fournir des informations d’emplacement lors de leur client inscrit à un nouvel emplacement. Les utilisateurs peuvent ignorer l’invite sans entrer les informations d’emplacement.
    
  - **Non requis** Sélectionnez cette option si les utilisateurs ne doivent ne pas fournir des informations d’emplacement.
    
  - **Exclusion de responsabilité** Sélectionnez cette option si les utilisateurs doivent fournir des informations d’emplacement, mais s’affichera un message d’avertissement si elles refuser l’invite sans entrer les informations. Les utilisateurs peuvent effectuer un appel d’urgence, mais pas d’autres appels avant d’avoir entré les informations d’emplacement.
    
- **Emplacement d’utilisation pour E9-1-1 uniquement** Activez cette case à cocher si les informations d’emplacement doit être utilisé uniquement pour les appels d’urgence.
    
- **Utilisation de TLS** Sélectionnez l’utilisation téléphonique commuté public network (PSTN) qui sera utilisée pour déterminer l’itinéraire de voix sera utilisé pour le routage des appels d’urgence à partir des clients qui utilisent ce profil. La gamme associée à cette utilisation doit pointer vers un SIP trunk dédié à des appels d’urgence ou à une passerelle de nombre de Identification d’emplacement en cas d’urgence (ELIN) qui achemine les appels d’urgence à la plus proche Public sécurité répondant pointez PSAP (). Les options sont **interne**, **Local**ou **longue distance**.
    
- **E9-1-1 à composer le numéro** Spécifiez le numéro à composer pour contacter les services d’urgence.
    
- **Composer le masque E9-1-1** Spécifiez un nombre qui se compose d’un utilisateur, qui est ensuite converti dans le nombre d’accès à distance en cas d’urgence. Par exemple, permet d’entrer une valeur de 212 dans ce champ afin qu’un utilisateur peut composer 212 pour accéder à des services d’urgence. Cela permet à d’autres numéros d’urgence à composer et toujours l’appel de contacter les services d’urgence (par exemple, si une personne d’un pays ou une région avec un autre numéro d’urgence tente de composer que pays ou région numérique de la plutôt que le numéro de la pays ou région dans que se trouvent actuellement). Vous pouvez définir plusieurs masques d’accès d’urgence en séparant les valeurs par des points-virgules. Par exemple, 212 ; 414. La longueur maximale de la chaîne est de 100 caractères. Chaque caractère doit être un chiffre de 0 à 9.
    
    > [!IMPORTANT]
    > Assurez-vous que le masque d’appel n’est pas identique à un numéro figurant dans une plage de numéros d’appels parqués, car l’acheminement du parcage d’appels est prioritaire sur la conversion des chaînes d’appel d’urgence. Pour voir les plages de numéros d’appel Park, cliquez sur **Fonctionnalités vocales** dans la barre de navigation gauche, puis cliquez sur **Appel Park**. 
  
- **URI de notification** Spécifiez un ou plusieurs des URI SIP pour être averti lors d’un appel d’urgence. Par exemple, tapez URI SIP de l’office de sécurité entreprise pour informer le personnel de sécurité avec un message instantané chaque fois qu’un appel d’urgence. Si l’emplacement de l’appelant n’est disponible, l’emplacement est inclus dans la notification. Vous pouvez spécifier plusieurs URI de SIP sous forme de liste séparée par des virgules. Par exemple, « sip:security@litwareinc.com », « sip:kmyer@litwareinc.com ». La chaîne doit être entre 1 et 256 caractères et doit commencer par le préfixe « sip : ». Vous pouvez également spécifier des listes de distribution.
    
- **URI de conférence** Spécifiez l’URI SIP (numéro de téléphone, dans ce cas) à des tiers d’être conferenced dans les appels d’urgence. Tapez, par exemple, le numéro de téléphone du bureau de sécurité de société afin qu’ils reçoivent un appel lors d’un appel d’urgence. Le paramètre de **mode de conférence** détermine si le tiers peut participer ou simplement écouter l’appel. La chaîne doit être entre 1 et 256 caractères et doit commencer par le panneau sip du préfixe :.
    
- **Mode conférence** Si vous avez spécifié une valeur pour **l’URI de la conférence**, définissez ce champ à l’une des valeurs suivantes :
    
  - **À sens unique** Spécifie que le tiers peut écouter uniquement à l’appel entre l’appelant et l’opérateur PSAP.
    
  - **Bidirectionnelle** Spécifie que le tiers peut participer à l’appel entre l’appelant et l’opérateur PSAP.
    
Pour plus d’informations sur les fonctionnalités de service d’urgence de Voix Entreprise de, consultez [vue d’ensemble de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation de stratégies d’emplacement, reportez-vous à la section [Configuration de la stratégie emplacement](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) dans la documentation sur les opérations.
  

