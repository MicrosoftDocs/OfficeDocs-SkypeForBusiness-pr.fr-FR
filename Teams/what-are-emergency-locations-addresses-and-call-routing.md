---
title: Quels sont les emplacements d’urgence, les adresses et le routage des appels ?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 7ce9d9ceecdfdb19d80e8d2b2fa3b45e4f330398
ms.sourcegitcommit: d7cab12337c0226c321e905a0504247fcff5eb77
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/27/2018
ms.locfileid: "26676543"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Quels sont les emplacements d’urgence, les adresses et le routage des appels ?

Lorsque vous configurez des Plans de l’appel dans Office 365, vous devez attribuer une adresse d’urgence pour chaque numéro de téléphone lorsque vous obtenez le numéro de téléphone ou l’attribuer à un utilisateur pour prendre en charge les appels d’urgence. Et avant de pouvoir affecter une adresse d’urgence pour un numéro de téléphone, vous devez créer et valider l’adresse en cas d’urgence. La validation garantit que l’adresse d’urgence est reconnue et qu’elle est dans un format correct qui peut être utilisé par les services d’urgence. Si vous le souhaitez, vous pouvez ajouter un emplacement au sein de l’adresse d’urgence pour fournir un emplacement plus spécifique pour l’utilisateur. Par exemple, l’emplacement d’urgence peut être un plancher, papillon ou office qui est liée à une adresse spécifique en cas d’urgence. Bien que l’adresse d’urgence sont validés, emplacements ne sont pas.
  
## <a name="what-are-emergency-addresses"></a>Que sont les adresses de secours ?

Une adresse d’urgence est requise pour les numéros de téléphone active, mais lorsqu’ils sont nécessaires dépend du pays ou région. Aux États-Unis, une adresse d’urgence est requise quand un numéro est affecté à un utilisateur. Pour d’autres pays, comme dans Europe, Moyen-Orient et Afrique (région EMEA), une adresse d’urgence est requise lorsque vous récupérez le numéro de téléphone à partir d’Office 365 ou lorsqu’elle est transférée à partir d’un autre fournisseur de services ou opérateur.
  
Une adresse d’urgence peut être appelée à une adresse postale, adresse postale ou une adresse physique. Il s'agit de la rue ou de l'adresse géographique du site d'activité de votre organisation. Par exemple, l’adresse *que 12345 Nord Main Street, Redmond, WA 98052* est utilisé pour acheminer les appels d’urgence pour les autorités de répartition appropriée et pour vous aider à localiser l’appelant d’urgence. Si votre organisation comporte plusieurs sites physiques, il est probable que vous aurez besoin de plusieurs adresses de secours.
  
Validation d’une adresse d’urgence consiste à s’assurer qu’elle est légitime et correctement mise en forme pour les services d’urgence. Il est possible de créer et enregistrer une adresse d’urgence qui n’est pas validée, mais seules les adresses validés peuvent être associés à un utilisateur. Une fois qu'une adresse de secours est validée et enregistrée, elle peut être affectée à un utilisateur. Si vous devez modifier une adresse de secours validée enregistrée, vous devrez en créer une autre.
  
## <a name="what-are-emergency-locations"></a>Que sont les emplacements d'urgence ?

Un emplacement d’urgence est associé à une adresse à un emplacement plus précis au sein d’un bâtiment en cas d’urgence. Un emplacement d'urgence peut être l'étage, l'aile d'un bâtiment ou le numéro du bureau où se trouve l'utilisateur. Vous pouvez avoir un nombre illimité d’emplacements associés à une adresse d’urgence. 
  
Lorsque vous attribuez une adresse d’urgence à un utilisateur, il est en fait un code d’emplacement qui est référencé lorsque vous attribuez l’adresse. Le code d’emplacement inclut l’adresse d’urgence référencé (ou l’adresse postale ou civiles). L’emplacement par défaut d’urgence est fourni avec une adresse d’urgence pour les cas dans lesquels les emplacements de construction ne sont pas nécessaires. 
  
## <a name="what-is-emergency-call-routing"></a>Qu'est-ce que le routage d'appel d'urgence ?

Emplacements et les adresses d’urgence sont utilisés au cours du processus de routage des appels d’urgence pour le centre d’expédition approprié lors de la répartition des premiers intervenants d’urgence. Lorsqu’un équipes ou Skype pour l’utilisateur compose un numéro d’urgence, comment l’appel est acheminé vers le service Public Safety Answering Point (PSAP) varient selon le pays/région. Dans certains pays, tels que les États-Unis et au Royaume-Uni, les appels seront tout d’abord être filtrés pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel vers le centre d’expédition approprié. Dans d’autres pays/régions, les appels seront acheminés directement au centre de distribution traiter le numéro de téléphone associé à l’appelant d’urgence.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Créer, ajouter et affecter des emplacements d’urgence et les adresses à vos utilisateurs

1. **Planifier des emplacements d’urgence**. La première étape consiste à planifier vos emplacements d’urgence. Vous devez répertorier toutes vos adresses physiques. Puis, selon que, déterminer si des emplacements pour les adresses d’urgence sont nécessaires et si c’est le cas, ce qu’ils sont. Par exemple, si une entreprise possède 3 bâtiments chaque avec 4 étages, il est probable que doit comporter 3 adresses d’urgence, avec étages répertorié en tant qu’emplacement pour chaque 1 à 4.
    
2. **Créer et valider vos emplacements d’urgence**. L’étape suivante consiste à créer et valider les adresses d’urgence. Lorsque vous créez une adresse de secours, vous pouvez la valider. Pour créer une adresse d’urgence, voir [Ajouter ou supprimer une situation d’urgence d’adresses pour votre organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > La validation d'une adresse postale ou d'une adresse géographique implique de vérifier sa légitimité et son format. Il est possible qu’une adresse d’urgence partiellement correcte, par exemple un nom de la ville, faute de frappe peut-être encore être validée. La procédure de validation utilise toutes les parties d'une adresse pour déterminer si l'adresse contient suffisamment d'informations et acheminer l'appel vers le centre de réception des appels d'urgence approprié. Dans ce cas, il s’afficheront comme validée et permettre être affecté à un numéro de téléphone. 
  
3. **Obtenir les numéros de téléphone**. L’étape suivante consiste à obtenir les numéros de téléphone pour vos utilisateurs. À cet effet, vous pouvez obtenir de nouveaux numéros de téléphone auprès d'Office 365 ou en « portant » ou en transférant vos numéros de téléphone existants vers Office 365. Pour voir la procédure complète, consultez [transfert des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Affecter des numéros de téléphone**. La dernière étape consiste à permettre aux utilisateurs d’émettre et recevoir des appels téléphoniques. Vous devez donc attribuer un numéro de téléphone à chaque utilisateur. Voir [affecter, modifier ou supprimer un numéro de téléphone d’un utilisateur](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) d’affecter un numéro de téléphone.

> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>Rubriques connexes
[Qu’est-ce que la validation d’adresse ?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Différents types de numéros de téléphone utilisés pour les forfaits d'appels](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

