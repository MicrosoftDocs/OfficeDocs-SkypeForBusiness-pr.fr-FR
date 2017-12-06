---
title: "Comment utiliser un ID d'appelant dans votre organisation"
ms.author: tonysmit
author: tonysmit
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
description: "ID de l'appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l'aide d'une stratégie nommée CallingLineIdentity."
---

# Comment utiliser un ID d'appelant dans votre organisation

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](5a0bd8ba-3334-46ee-becf-1025597737f6.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/5a0bd8ba-3334-46ee-becf-1025597737f6). 
  
ID de l'appelant peut être contrôlée pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l'aide d'une stratégie nommée CallingLineIdentity.
  
La fonctionnalité d'ID de l'appelant est disponible pour tous les utilisateurs système téléphonique quelle que soit la connectivité PSTN :
  
- Connectivité RTC en ligne
    
- Connectivité RTC locale avec Skype Entreprise, Édition Cloud Connector (requiert Cloud Connector Édition 1.4.2 et version ultérieure)
    
- Connectivité RTC locale avec Skype Entreprise Server (requiert Skype Entreprise Server 2015 CU5 et version ultérieure)
    
> [!NOTE]
> Cette stratégie n'est pas disponible pour Skype Entreprise 2015 Server. 
  
## ID d'appelant sortant

Trois options sont disponibles pour l'ID d'appelant RTC sortant :
  
- Le numéro de téléphone affecté à l'utilisateur, ce qui correspond à la valeur par défaut.
    
- Un numéro de téléphone est considéré comme un  *service*  et un numéro de *numéro gratuit*  dans votre appel d'offre dans Office 365 téléphone numéro inventaire. Il est généralement affecté à une file d'attente standard ou appel automatique d'organisation.
    
- Défini sur Anonyme.
    
Toutefois, vous ne pouvez pas affecter les types de numéros de téléphone suivants à l'ID d'appelant entrant :
  
- Les numéros de téléphone sont classés en tant qu'  *utilisateur*  dans votre téléphone appel d'offre nombre stock
    
- Un numéro de téléphone Skype Entreprise Server local
    
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
### Contrôle de l'ID d'appelant sortant par l'utilisateur final

L'attribut EnableUserOverride permet un ou plusieurs utilisateurs à modifier leur paramètre ID de l'appelant **anonyme**. Cela s'applique uniquement lorsqu'une stratégie CallingLineIdentity est configurée avec un paramètre CallingIDSubstitute de LineURI ou substitue. La valeur par défaut de EnableUserOverride est faux.
  
Vos utilisateurs pouvez définir leur ID d'appelant **anonyme** à l'aide de l'onglet **Paramètres d'appel vers l'avant** dans le Skype pour client de bureau d'entreprise.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Version** <br/> |**Prise en charge** <br/> |
|Démarrer en un clic  <br/> |Canal actuel publié le 6 décembre 2016 - version 1611 (Build 7571.2072)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Première version du canal différé publiée le 22 février 2017 - version 1701 (Build 7766.2060)  <br/> |Oui  <br/> |
|Démarrer en un clic  <br/> |Différé canal publié sur 13 juin 2017 - Version 1701 (Build 7766.2092)  <br/> |Oui  <br/> |
|MSI  <br/> |Skype Entreprise  <br/> |Non  <br/> |
|Mac  <br/> |Skype Entreprise  <br/> |Non  <br/> |
   
Vos utilisateurs finaux peuvent également définir leur paramètre d'ID d'appelant sur la page des paramètres utilisateur en se rendant sur : [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
  
## ID d'appelant entrant

L'attribut BlockIncomingCallerID permet de blocage de l'ID d'appelant pour les appels entrants PSTN. Vous pouvez définir cet attribut, mais il n'est pas disponible pour les utilisateurs finaux dans la page de paramètres utilisateur. Et il est actuellement disponible uniquement avec une connectivité PSTN en ligne.
  
Pour définir l'ID d'appelant sortant, reportez-vous à la rubrique [Définir l'ID d'appelant d'un utilisateur](set-the-caller-id-for-a-user.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  
[Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

