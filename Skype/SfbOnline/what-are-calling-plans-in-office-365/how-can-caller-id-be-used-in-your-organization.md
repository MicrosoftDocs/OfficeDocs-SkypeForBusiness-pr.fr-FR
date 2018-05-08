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
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Comment utiliser un ID d'appelant dans votre organisation

ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
  
La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique quelle que soit la connectivité PSTN :
  
- Connectivité RTC en ligne
    
- Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)
    
- Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)
    
> [!NOTE]
> Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server. 
  
## <a name="outbound-caller-id"></a>ID d'appelant sortant

Trois options sont disponibles pour l'ID d'appelant RTC sortant :
  
- Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.
    
- Un numéro de téléphone qui est considéré comme un *service* et un *numéro gratuit* nombre dans vos Plans de l’appel dans Office 365 téléphone numéro inventaire. Il est généralement attribué à une file d’attente d’organisation automatique standard ou un appel.
    
- Défini sur Anonyme.
    
Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :
  
- Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone de l’appel des Plans de numéro d’inventaire
    
- Un numéro de téléphone Skype Entreprise Server local
    
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle de l'ID d'appelant sortant par l'utilisateur final

L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs à modifier leurs paramètres d’ID de l’appelant **anonyme**. Cela s’applique uniquement lorsqu’une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute de LineURI ou de remplacement. La valeur par défaut de EnableUserOverride a la valeur False.
  
Vos utilisateurs finaux peuvent définir leur ID d’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appel vers l’avant** dans le Skype pour le client de bureau d’entreprise.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Prise en charge** <br/> |
|Démarrer en un clic  <br/> |Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Différé canal publié le 13 juin 2017 - Version 1701 (Build 7766.2092)  <br/> |Oui  <br/> |
|MSI  <br/> |Skype Entreprise  <br/> |Non  <br/> |
|Mac  <br/> |Skype Entreprise  <br/> |Non  <br/> |
   
## <a name="inbound-caller-id"></a>ID d'appelant entrant

L’attribut BlockIncomingCallerID permet de blocage de l’ID d’appelant pour les appels PSTN entrants. Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux dans la page de paramètres utilisateur. Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.
  
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 