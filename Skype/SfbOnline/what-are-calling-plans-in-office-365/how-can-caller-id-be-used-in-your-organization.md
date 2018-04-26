---
title: Comment utiliser un ID d'appelant dans votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity.
ms.openlocfilehash: 4dc596e8301310f2c229c46add5795e72c432daf
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Comment utiliser un ID d'appelant dans votre organisation

ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity.
  
La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique que connectivité RTPC :
  
- Connectivité RTC en ligne
    
- Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)
    
- Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)
    
> [!NOTE]
> Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server. 
  
## <a name="outbound-caller-id"></a>ID d'appelant sortant

Trois options sont disponibles pour l'ID d'appelant RTC sortant :
  
- Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.
    
- Numéro de stock un numéro de téléphone qui est considéré comme un *service* et un numéro *d’appel gratuit* dans vos Plans de l’appel dans téléphone d’Office 365. Il est généralement affecté à une file d’attente surveillance du ou des appels d’organisation automatique.
    
- Défini sur Anonyme.
    
Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :
  
- Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone appel Plans numéro de stock
    
- Un numéro de téléphone Skype Entreprise Server local
    
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle de l'ID d'appelant sortant par l'utilisateur final

L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs à modifier leurs paramètres d’ID de l’appelant **anonyme**. Cela s’applique uniquement lorsqu’une stratégie de CallingLineIdentity est configurée avec un paramètre de CallingIDSubstitute de LineURI ou de substitution. La valeur par défaut de EnableUserOverride a la valeur False.
  
Vos utilisateurs finaux peuvent définir leur ID de l’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appeler vers l’avant** dans le Skype pour client ordinateur de bureau d’entreprise.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Prise en charge** <br/> |
|Démarrer en un clic  <br/> |Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Différé de canal publié le 13 juin 2017 - Version 1701 (Build 7766.2092)  <br/> |Oui  <br/> |
|MSI  <br/> |Skype Entreprise  <br/> |Non  <br/> |
|Mac  <br/> |Skype Entreprise  <br/> |Non  <br/> |
   
## <a name="inbound-caller-id"></a>ID d'appelant entrant

L’attribut BlockIncomingCallerID permet de blocage de l’ID d’appelant pour les appels entrants RTPC. Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux sur la page Paramètres de l’utilisateur. Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.
  
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 