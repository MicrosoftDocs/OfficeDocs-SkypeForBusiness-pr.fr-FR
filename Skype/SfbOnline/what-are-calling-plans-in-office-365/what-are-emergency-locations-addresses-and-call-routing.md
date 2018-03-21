---
title: Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 35553da49cbaffde1a960ce83550b6fc4ce3ef07
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?

Lorsque vous configurez l’appel de Plans dans Office 365, il est nécessaire qu’une adresse d’urgence être affecté à chaque numéro de téléphone lorsque vous les avez le numéro de téléphone ou son affectées à un utilisateur de prendre en charge de l’appel d’urgence. Avant d’assigner une adresse d’urgence à un numéro de téléphone, une adresse d’urgence doit être créée et validée. La validation garantit que l’adresse d’urgence est reconnu et qu’il est dans un format correct qui peut être utilisé par les services d’intervention d’urgence. Le cas échéant, un emplacement de l’adresse d’urgence peut être ajouté pour fournir un emplacement plus spécifique pour l’utilisateur. Par exemple, l’emplacement d’urgence peut être un étage, aile ou office qui est lié à une adresse de secours spécifique. Même si l’adresse d’urgence sont validées, les emplacements ne sont pas.
  
## <a name="what-are-emergency-addresses"></a>Que sont les adresses de secours ?

Une adresse d’urgence est requise pour les numéros de téléphone active, mais lorsqu’ils sont nécessaires dépendent du pays/région. Aux États-Unis, une adresse d’urgence est **nécessaire** quand un numéro est affecté à un utilisateur. Pour d’autres pays, par exemple en Europe, le Moyen-Orient et l’Afrique (EMEA), une adresse d’urgence est **nécessaire** lorsque vous obtenez le numéro de téléphone à partir d’Office 365, ou lorsqu’il est transféré à partir d’un autre fournisseur de services ou le transporteur.
  
Une adresse d’urgence peut correspondre à une adresse postale, adresse ou une adresse physique. Il s'agit de la rue ou de l'adresse géographique du site d'activité de votre organisation. Par exemple, l’adresse *que 12345 Nord Main Street, Redmond, WA 98052* est utilisé pour acheminer les appels d’urgence les autorités de répartition appropriée et pour vous aider à localiser l’appelant en cas d’urgence. Si votre organisation comporte plusieurs sites physiques, il est probable que vous aurez besoin de plusieurs adresses de secours.
  
Validation d’une adresse d’urgence consiste à s’assurer qu’il est légitime et correctement mis en forme pour les services d’intervention d’urgence. Il est possible de créer et d’enregistrer une adresse d’urgence qui n’est pas validée, mais uniquement les adresses validées peuvent être associées à un utilisateur. Une fois qu'une adresse de secours est validée et enregistrée, elle peut être affectée à un utilisateur. Si vous devez modifier une adresse de secours validée enregistrée, vous devrez en créer une autre.
  
## <a name="what-are-emergency-locations"></a>Que sont les emplacements d'urgence ?

Emplacements d’urgence sont associés à une adresse d’urgence à donner à un emplacement plus exact d’un bâtiment. Un emplacement d'urgence peut être l'étage, l'aile d'un bâtiment ou le numéro du bureau où se trouve l'utilisateur. Vous pouvez avoir un nombre illimité d’emplacements associés à une adresse en cas d’urgence. 
  
Lorsque vous affectez une adresse de secours à un utilisateur, il s'agit en fait d'un ID d'emplacement référencé lors de l'affectation de l'adresse. Le code d’emplacement inclut l’adresse de secours référencé (l’adresse postale ou civique). Un emplacement d'urgence par défaut est inclus avec une adresse de secours au cas où des emplacements internes aux bâtiments ne seraient pas nécessaires. 
  
## <a name="what-is-emergency-call-routing"></a>Qu'est-ce que le routage d'appel d'urgence ?

Emplacements et adresses d’urgence sont utilisés au cours du processus d’acheminement d’appels d’urgence au centre de répartition appropriée lors de l’envoi d’urgence premiers intervenants. Lorsqu’un Skype pour l’utilisateur professionnel compose un numéro en cas d’urgence, comment l’appel est acheminé vers le service Public sécurité répondant Point PSAP () varie selon le pays/région. Dans certains pays, tels que les États-Unis et le Royaume-Uni, les appels sont tout d’abord être filtrés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel vers le centre d’expédition approprié. Dans d’autres pays/régions, les appels sont routés directement vers le centre d’expédition desservant le numéro de téléphone associé à l’appelant en cas d’urgence.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Création, ajout et affectation d’emplacements d’urgence et des adresses à vos utilisateurs

1. **Planifier les emplacements d’urgence** La première étape consiste à planifier pour vos emplacements d’urgence. Vous devez répertorier toutes vos adresses physiques. Puis, sur cette base, déterminez si les emplacements pour les adresses d’urgence sont nécessaires et dans l’affirmative, quelles qu’elles sont. Par exemple, si une entreprise a 3 immeubles de bureaux chaque avec 4 étages, il est probable qu’il faudra 3 adresses en cas d’urgence, avec étages 1 à 4 est répertorié comme un emplacement pour chaque.
    
2. **Création et validation de vos emplacements d'urgence** L'étape suivante consiste à créer et à valider vos adresses de secours. Lorsque vous créez une adresse de secours, vous pouvez la valider. Pour créer une adresse en cas d’urgence, consultez [Ajouter ou supprimer d’urgence d’adresses pour votre organisation](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > La validation d'une adresse postale ou d'une adresse géographique implique de vérifier sa légitimité et son format. Il est possible qu’une adresse d’urgence qui n’est que partiellement correcte, comme une faute de frappe dans le nom de la ville, soit tout de même validée. La procédure de validation utilise toutes les parties d'une adresse pour déterminer si l'adresse contient suffisamment d'informations et acheminer l'appel vers le centre de réception des appels d'urgence approprié. Dans ce cas, il sera retourné comme validé et puis, peut être affecté à un numéro de téléphone. 
  
3. **Obtenir les numéros de téléphone** L’étape suivante consiste à obtenir les numéros de téléphone pour vos utilisateurs. À cet effet, vous pouvez obtenir de nouveaux numéros de téléphone auprès d'Office 365 ou en « portant » ou en transférant vos numéros de téléphone existants vers Office 365. Pour consulter la procédure complète, consultez le [transfert vers Office 365, les numéros de téléphone](transfer-phone-numbers-to-office-365.md).
    
4. **Attribution des numéros de téléphone** La dernière étape consiste à autoriser les utilisateurs à passer et à recevoir des appels téléphoniques. Vous devez donc attribuer un numéro de téléphone à chaque utilisateur. Reportez-vous à la section [affecter, modifier ou supprimer un numéro de téléphone d’un utilisateur](assign-change-or-remove-a-phone-number-for-a-user.md) d’affecter un numéro de téléphone.

> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>Rubriques connexes
[Qu’est-ce que la validation d’adresse ?](what-is-address-validation.md)

[Différents types de numéros de téléphone utilisés pour les forfaits d'appels](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales relatives aux appels d'urgence](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://go.microsoft.com/fwlink/?LinkID=692099)
