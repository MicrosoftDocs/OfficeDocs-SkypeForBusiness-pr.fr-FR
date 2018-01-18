---
title: Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: b6f9ffcbba68a7892a137a68565de97fe390d00f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?

Lorsque vous configurez l’appel de Plans dans Office 365, il est nécessaire qu’une adresse d’urgence être affecté à chaque numéro de téléphone lorsque vous les avez le numéro de téléphone ou son affectées à un utilisateur de prendre en charge de l’appel d’urgence. Avant d’assigner une adresse d’urgence à un numéro de téléphone, une adresse d’urgence doit être créée et validée. La validation garantit que l’adresse d’urgence est reconnu et qu’il est dans un format correct qui peut être utilisé par les services d’intervention d’urgence. Le cas échéant, un emplacement de l’adresse d’urgence peut être ajouté pour fournir un emplacement plus spécifique pour l’utilisateur. Par exemple, l’emplacement d’urgence peut être un étage, aile ou office qui est lié à une adresse de secours spécifique. Même si l’adresse d’urgence sont validées, les emplacements ne sont pas.
  
## <a name="what-are-emergency-addresses"></a>Que sont les adresses de secours ?

Une adresse d’urgence est requise pour les numéros de téléphone active, mais lorsqu’ils sont nécessaires dépendent du pays/région. Aux États-Unis, une adresse d’urgence est **nécessaire** quand un numéro est affecté à un utilisateur. Pour d’autres pays, par exemple en Europe, le Moyen-Orient et l’Afrique (EMEA), une adresse d’urgence est **nécessaire** lorsque vous obtenez le numéro de téléphone à partir d’Office 365, ou lorsqu’il est transféré à partir d’un autre fournisseur de services ou le transporteur.
  
Une adresse d’urgence peut correspondre à une adresse postale, adresse ou une adresse physique. Il s’agit de l’adresse postale ou postale d’un lieu d’activité pour votre organisation. Par exemple, l’adresse *que 12345 Nord Main Street, Redmond, WA 98052* est utilisé pour acheminer les appels d’urgence les autorités de répartition appropriée et pour vous aider à localiser l’appelant en cas d’urgence. Il est probable que vous aurez besoin de plus d’une adresse d’urgence si votre entreprise a plus d’une implantation physique.
  
Validation d’une adresse d’urgence consiste à s’assurer qu’il est légitime et correctement mis en forme pour les services d’intervention d’urgence. Il est possible de créer et d’enregistrer une adresse d’urgence qui n’est pas validée, mais uniquement les adresses validées peuvent être associées à un utilisateur. Une fois une adresse d’urgence est validée et enregistrée, il peut être affecté à un utilisateur. Si vous devez changer l’adresse enregistrée validée en cas d’urgence, vous devrez créer un nouveau.
  
## <a name="what-are-emergency-locations"></a>Que sont les emplacements d'urgence ?

Emplacements d’urgence sont associés à une adresse d’urgence à donner à un emplacement plus exact d’un bâtiment. Un emplacement de secours est en général un plancher, aile d’un bâtiment ou un numéro de bureau où se trouve l’utilisateur. Vous pouvez avoir un nombre illimité d’emplacements associés à une adresse en cas d’urgence. 
  
Lorsque vous attribuez à un utilisateur une adresse en cas d’urgence, il est en fait un code d’emplacement qui est référencé lorsque vous affectez l’adresse. Le code d’emplacement inclut l’adresse de secours référencé (l’adresse postale ou civique). Un emplacement de secours par défaut est fourni avec une adresse d’urgence pour le cas lorsque les emplacements de construction ne sont pas nécessaires. 
  
## <a name="what-is-emergency-call-routing"></a>Qu'est-ce que le routage d'appel d'urgence ?

Emplacements et adresses d’urgence sont utilisés au cours du processus d’acheminement d’appels d’urgence au centre de répartition appropriée lors de l’envoi d’urgence premiers intervenants. Lorsqu’un Skype pour l’utilisateur professionnel compose un numéro en cas d’urgence, comment l’appel est acheminé vers le service Public sécurité répondant Point PSAP () varie selon le pays/région. Dans certains pays, tels que les États-Unis et le Royaume-Uni, les appels sont tout d’abord être filtrés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel vers le centre d’expédition approprié. Dans d’autres pays/régions, les appels sont routés directement vers le centre d’expédition desservant le numéro de téléphone associé à l’appelant en cas d’urgence.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Création, ajout et affectation d’emplacements d’urgence et des adresses à vos utilisateurs

1. **Planifier les emplacements d’urgence** La première étape consiste à planifier pour vos emplacements d’urgence. Vous devez répertorier toutes vos adresses physiques. Puis, sur cette base, déterminez si les emplacements pour les adresses d’urgence sont nécessaires et dans l’affirmative, quelles qu’elles sont. Par exemple, si une entreprise a 3 immeubles de bureaux chaque avec 4 étages, il est probable qu’il faudra 3 adresses en cas d’urgence, avec étages 1 à 4 est répertorié comme un emplacement pour chaque.
    
2. **Créer et valider vos emplacements d’urgence** L’étape suivante consiste à créer et valider vos adresses en cas d’urgence. Lorsque vous créez une adresse en cas d’urgence, vous pouvez la valider. Pour créer une adresse en cas d’urgence, consultez [Ajouter ou supprimer d’urgence d’adresses pour votre organisation](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Validation d’une adresse de rue ou civique consiste à s’assurer qu’il est légitime et correctement mis en forme. Il est possible qu’une adresse d’urgence partiellement correcte, par exemple un nom de la ville, de faute de frappe peut toujours passent le contrôle de la passe. Le processus de validation utilise toutes les parties d’une adresse donnée afin de déterminer si elle contient suffisamment d’informations pour acheminer l’appel vers le centre de répartition d’urgence appropriée. Dans ce cas, il sera retourné comme validé et puis, peut être affecté à un numéro de téléphone. 
  
3. **Obtenir les numéros de téléphone** L’étape suivante consiste à obtenir les numéros de téléphone pour vos utilisateurs. Pour cela en obtenant les nouveaux numéros de téléphone à partir d’Office 365, ou par un « portage » ou le transfert de vos numéros de téléphone existant sur vers Office 365. Pour consulter la procédure complète, consultez le [transfert vers Office 365, les numéros de téléphone](transfer-phone-numbers-to-office-365.md).
    
4. **Affecter des numéros de téléphone** La dernière étape consiste à permettre aux utilisateurs d’effectuer et de recevoir des appels téléphoniques. Pour ce faire, vous devez affecter un numéro de téléphone pour chaque utilisateur. Reportez-vous à la section [affecter, modifier ou supprimer un numéro de téléphone d’un utilisateur](assign-change-or-remove-a-phone-number-for-a-user.md) d’affecter un numéro de téléphone.

> [!NOTE]
> Si vous avez besoin obtenir des numéros de téléphone supplémentaires que cela, veuillez [contacter le support technique pour les produits d’entreprise - aide de l’administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>Rubriques connexes
[Quelle est la validation des adresses ?](what-is-address-validation.md)

[Différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales relatives aux appels d'urgence](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence](https://go.microsoft.com/fwlink/?LinkID=692099)
