---
title: Quels sont les emplacements d’urgence, les adresses et le routage des appels?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: c7e1bb719f0292bd605f920517017d2d4f6cae65
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288157"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>Quels sont les emplacements d’urgence, les adresses et le routage des appels?

Lorsque vous configurez des forfaits d’appels dans Office 365, vous devez attribuer une adresse d’urgence à chaque numéro de téléphone lorsque vous récupérez le numéro de téléphone ou attribuez-le à un utilisateur pour qu’il prenne en charge les appels d’urgence. Pour pouvoir affecter une adresse d’urgence à un numéro de téléphone, vous devez créer et valider l’adresse d’urgence. La validation vérifie que l’adresse de secours est reconnue et qu’elle est dans un format approprié qui peut être utilisé par les services de réponse d’urgence. Si vous le souhaitez, vous pouvez ajouter un emplacement au sein de l’adresse de secours pour fournir un emplacement plus précis pour l’utilisateur. Par exemple, l’emplacement d’urgence peut être un étage, une aile ou un bureau qui est lié à une adresse de secours spécifique. Même si l’adresse de secours est validée, les emplacements ne le sont pas.
  
## <a name="what-are-emergency-addresses"></a>Que sont les adresses de secours ?

Une adresse de secours est requise pour les numéros de téléphone actifs, mais lorsqu’elle est requise dépend du pays/de la région. Aux États-Unis, une adresse de secours est requise lorsqu’un numéro est attribué à un utilisateur. Dans d’autres pays (par exemple, en Europe, au Moyen-Orient et en Afrique), une adresse d’urgence est requise lorsque vous recevez le numéro de téléphone d’Office 365 ou lorsqu’il est transféré à partir d’un autre fournisseur ou opérateur de services.
  
Une adresse de secours doit être désignée sous le nom d’une adresse postale, d’une adresse postale ou d’une adresse physique. Il s'agit de la rue ou de l'adresse géographique du site d'activité de votre organisation. Par exemple, l’adresse *12345 North rue, Redmond, WA 98052* est utilisée pour diriger les appels d’urgence vers les autorités de répartition compétentes et pour faciliter la localisation de l’appelant d’urgence. Si votre organisation comporte plusieurs sites physiques, il est probable que vous aurez besoin de plusieurs adresses de secours.
  
La validation d’une adresse de secours implique de vérifier qu’elle est légitime et correctement mise en forme pour les services de réponse d’urgence. Il est possible de créer et enregistrer une adresse d’urgence qui n’est pas validée, mais seules les adresses validées peuvent être associées à un utilisateur. Une fois qu'une adresse de secours est validée et enregistrée, elle peut être affectée à un utilisateur. Si vous devez modifier une adresse de secours validée enregistrée, vous devrez en créer une autre.
  
## <a name="what-are-emergency-locations"></a>Que sont les emplacements d'urgence ?

Un emplacement d’urgence est associé à une adresse de secours pour fournir un emplacement plus précis au sein d’un bâtiment. Un emplacement d'urgence peut être l'étage, l'aile d'un bâtiment ou le numéro du bureau où se trouve l'utilisateur. Vous pouvez avoir un nombre illimité d’emplacements associés à une adresse de secours. 
  
Lorsque vous attribuez une adresse d’urgence à un utilisateur, il s’agit en fait d’un ID d’emplacement qui est référencé lors de l’affectation de l’adresse. L’ID d’emplacement inclut l’adresse de secours référencée (rue ou adresse postale). Un emplacement d’urgence par défaut est inclus dans une adresse de secours dans les cas où les emplacements en bâtiment ne sont pas nécessaires. 
  
## <a name="what-is-emergency-call-routing"></a>Qu'est-ce que le routage d'appel d'urgence ?

Les adresses d’urgence et les emplacements d’urgence sont utilisés lors du processus de routage des appels d’urgence vers le centre de répartition approprié lors de la distribution des premiers répondants d’urgence. Lorsqu’un utilisateur de teams ou de Skype entreprise compose un numéro d’urgence, le routage de l’appel vers le point de connexion à la sécurité publique (PSAPI) dépend du pays/de la région. Dans certains pays (par exemple, les États-Unis et le Royaume-Uni), les appels seront d’abord affichées pour déterminer l’emplacement actuel de l’utilisateur avant de connecter l’appel au centre de répartition approprié. Dans d’autres pays ou régions, les appels seront routés directement vers le centre de répartition qui dessert le numéro de téléphone associé à l’appelant d’urgence.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Créer, ajouter et affecter des emplacements et des adresses de secours à vos utilisateurs

1. **Planifiez les emplacements d’urgence**. La première étape consiste à planifier vos emplacements d’urgence. Vous devez dresser la liste de toutes vos adresses physiques. En fonction de cela, déterminez si des emplacements pour les adresses d’urgence sont nécessaires et, le cas échéant, ce qu’ils représentent. Par exemple, dans le cas d’une entreprise ayant 3 immeubles de bureau avec 4 étages, il est probable qu’il y ait 3 adresses d’urgence, dont l’emplacement est indiqué par l’emplacement 1-4.
    
2. **Créez et validez vos emplacements d’urgence**. L’étape suivante consiste à créer et valider vos adresses de secours. Lorsque vous créez une adresse de secours, vous pouvez la valider. Pour créer une adresse de secours, reportez-vous à [la rubrique Ajout ou suppression d’une adresse de secours pour votre organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > La validation d'une adresse postale ou d'une adresse géographique implique de vérifier sa légitimité et son format. Il est possible qu’une adresse de secours partiellement correcte (par exemple, le nom de la ville, par exemple) puisse rester valide. La procédure de validation utilise toutes les parties d'une adresse pour déterminer si l'adresse contient suffisamment d'informations et acheminer l'appel vers le centre de réception des appels d'urgence approprié. Si tel est le cas, il sera renvoyé comme validé et peut être attribué à un numéro de téléphone. 
  
3. **Obtenez des numéros de téléphone**. L’étape suivante consiste à obtenir des numéros de téléphone pour vos utilisateurs. À cet effet, vous pouvez obtenir de nouveaux numéros de téléphone auprès d'Office 365 ou en « portant » ou en transférant vos numéros de téléphone existants vers Office 365. Pour consulter les étapes complètes, voir [transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Attribution de numéros de téléphone**. La dernière étape consiste à permettre aux utilisateurs de passer et de recevoir des appels téléphoniques. Vous devez donc attribuer un numéro de téléphone à chaque utilisateur. Pour attribuer un numéro de téléphone, reportez-vous à la section [affectation, modification ou suppression du numéro de téléphone d’un utilisateur](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) .

> [!NOTE]
> Si vous devez obtenir davantage de numéros de téléphone, veuillez [contacter le support pour les entreprises - Aide de l'administrateur](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>Rubriques connexes
[Qu’est-ce que la validation d’adresse ?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Différents types de numéros de téléphone utilisés pour les appels d’offre](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

