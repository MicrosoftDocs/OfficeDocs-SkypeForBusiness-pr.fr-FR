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
search.appverid: MET150
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
description: L’ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 410712a8fd0a6f28b0bc2821daae8143b38ceb63
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854224"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Comment utiliser un ID d'appelant dans votre organisation

L’ID de l’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
  
La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique quelle que soit la connectivité PSTN :
  
- Connectivité RTC en ligne
    
- Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)
    
- Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)
    
> [!NOTE]
> Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server. 
  
## <a name="outbound-caller-id"></a>ID d'appelant sortant

Trois options sont disponibles pour l'ID d'appelant RTC sortant :
  
- Le numéro de téléphone affecté à l’utilisateur (option par défaut).
    
- Un numéro de téléphone considéré comme un numéro *de service* et *gratuit* dans votre stock de numéros de téléphones de vos Forfaits d’appels dans Office 365. Il est généralement attribué à un standard automatique d’organisation ou à une file d’appels.
    
- Défini sur Anonyme.
    
Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :
  
- Tout numéro de téléphone classé comme  *utilisateur*  dans votre stock de numéros de téléphone de vos Forfaits d’appels
    
- Un numéro de téléphone Skype Entreprise Server local
    
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle de l'ID d'appelant sortant par l'utilisateur final

L'attribut EnableUserOverride permet à un ou plusieurs utilisateurs de modifier leur paramètre d'ID d'appelant pour le définir sur **Anonyme**. Cela s'applique uniquement lorsqu'une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute défini sur LineURI ou Substitute. La valeur par défaut de EnableUserOverride est False.
  
Vos utilisateurs finaux peuvent définir leur ID d’appelant sur **Anonyme** à l’aide de l’onglet **Paramètres de transfert d’appel** dans le client de bureau Skype Entreprise.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Prise en charge** <br/> |
|Démarrer en un clic  <br/> |Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Canal Différé publié le 13 juin 2017 - Version 1701 (Build 7766.2092)  <br/> |Oui  <br/> |
|MSI  <br/> |Skype Entreprise  <br/> |Non  <br/> |
|Mac  <br/> |Skype Entreprise  <br/> |Non  <br/> |
   
## <a name="inbound-caller-id"></a>ID d'appelant entrant

L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants. Vous pouvez définir cet attribut, mais il n’est pas disponible pour vos utilisateurs finaux sur la page des paramètres utilisateur. Pour le moment, il est disponible uniquement avec la connectivité RTC en ligne.
  
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](/microsoftteams/transferring-phone-numbers-common-questions)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 