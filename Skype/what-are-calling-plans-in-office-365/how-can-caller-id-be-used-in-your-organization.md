---
title: "ID de l’appelant utilisation dans votre organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>ID de l’appelant utilisation dans votre organisation

ID de l’appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie nommée CallingLineIdentity.
  
La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique que connectivité RTPC :
  
- Connectivité RTPC en ligne
    
- La connectivité RTPC local avec Skype pour connecteur de nuage Professionnel (requiert le nuage connecteur Edition 1.4.2 et au-delà)
    
- Connectivité RTPC local avec Skype pour Business Server (nécessite Skype pour Business Server 2015 CU5 et au-delà)
    
> [!NOTE]
> Cette stratégie n’est pas disponible dans Skype pour Business Server de 2015. 
  
## <a name="outbound-caller-id"></a>ID de l’appelant sortant

Trois options sont disponibles pour l’ID de l’appelant RTPC sortant :
  
- Le numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.
    
- Numéro de stock un numéro de téléphone qui est considéré comme un *service* et un numéro *d’appel gratuit* dans vos Plans de l’appel dans téléphone d’Office 365. Il est généralement affecté à une file d’attente surveillance du ou des appels d’organisation automatique.
    
- La valeur anonyme.
    
Toutefois, vous ne pouvez pas affecter ces types de numéros de téléphone pour l’ID d’appelant sortant :
  
- Les numéros de téléphone qui sont classés en tant qu' *utilisateur* de votre téléphone appel Plans numéro de stock
    
- Un Skype pour le numéro de téléphone local Business Server
    
Pour définir l’ID d’appelant sortants, consultez [la valeur de l’ID d’appelant pour un utilisateur](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle de l’utilisateur final de l’ID de l’appelant sortant

L’attribut EnableUserOverride permet à un ou plusieurs utilisateurs à modifier leurs paramètres d’ID de l’appelant **anonyme**. Cela s’applique uniquement lorsqu’une stratégie de CallingLineIdentity est configurée avec un paramètre de CallingIDSubstitute de LineURI ou de substitution. La valeur par défaut de EnableUserOverride a la valeur False.
  
Vos utilisateurs finaux peuvent définir leur ID de l’appelant **anonyme** à l’aide de l’onglet **Paramètres d’appeler vers l’avant** dans le Skype pour client ordinateur de bureau d’entreprise.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Prise en charge** <br/> |
|Démarrer en un clic  <br/> |Canal de cours publié le 6 décembre 2016 - version 1611 (Build 7571.2072)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Première version différé canal publié le 22 février 2017 - Version 1701 (Build 7766.2060)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Différé de canal publié le 13 juin 2017 - Version 1701 (Build 7766.2092)  <br/> |Oui  <br/> |
|MSI  <br/> |Skype Entreprise  <br/> |Non  <br/> |
|Mac  <br/> |Skype Entreprise  <br/> |Non  <br/> |
   
## <a name="inbound-caller-id"></a>ID de l’appelant entrant

L’attribut BlockIncomingCallerID permet de blocage de l’ID d’appelant pour les appels entrants RTPC. Vous pouvez définir cet attribut, mais il n’est pas disponible pour les utilisateurs finaux sur la page Paramètres de l’utilisateur. Et elle n’est disponible qu’avec connectivité RTPC en ligne.
  
Pour définir l’ID d’appelant sortants, consultez [la valeur de l’ID d’appelant pour un utilisateur](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Transfert de questions courantes des numéros de téléphone](transferring-phone-numbers-common-questions.md)

[Différents types de numéros de téléphone utilisés pour les Plans d’appel](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer les numéros de téléphone pour votre organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)

[Skype pour Business Online : étiquette de décharge de responsabilité d’appel d’urgence](https://go.microsoft.com/fwlink/?LinkID=692099)