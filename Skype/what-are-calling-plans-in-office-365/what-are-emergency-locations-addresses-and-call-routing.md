---
title: "Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# Que sont les emplacements d'urgence, les adresses de secours et le routage des appels ?

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Lorsque vous configurez l'appel d'offre dans Office 365, il est nécessaire qu'une adresse d'urgence être affectée à chaque numéro de téléphone lorsque vous les avez le numéro de téléphone ou son affectée à un utilisateur pour prendre en charge l'appel d'urgence. Avant d'assigner une adresse d'urgence à un numéro de téléphone, une adresse d'urgence doit être créée et validée. La validation garantit que l'adresse d'urgence est reconnu et qu'il est dans un format correct qui peut être utilisé par les services d'urgence. Vous pouvez également un emplacement au sein de l'adresse d'urgence peut être ajouté à fournir un emplacement plus spécifique pour l'utilisateur. Par exemple, l'emplacement d'urgence peut être un étage, papillon ou office qui est lié à une adresse d'urgence spécifique. Même si l'adresse d'urgence sont validées, emplacements ne sont pas.
  
## Que sont les adresses de secours ?

Une adresse d'urgence est requise pour les numéros de téléphone active, mais lorsqu'ils sont nécessaires dépendant le pays/région. Aux États-Unis, une adresse d'urgence est **requise** lorsqu'un nombre est affecté à un utilisateur. Pour d'autres pays, comme dans Europe, Moyen Orient et Afrique (EMEA), une adresse d'urgence est **requis** lorsque vous recevez le numéro de téléphone à partir d'Office 365 ou lorsqu'il est transféré à partir d'un autre fournisseur de services ou carrier.
  
Une adresse d'urgence peut être appelée une adresse postale, adresse postale ou une adresse physique. Il est l'adresse postale ou civil d'un emplacement d'entreprise pour votre organisation. Par exemple, l'adresse  *que 12345 Amérique principaux rue, Redmond, WA 98052*  est utilisé pour acheminer les appels d'urgence vers les autorités de répartition appropriée et aident à localiser l'appelant d'urgence. Il est probable que vous aurez besoin de plusieurs adresses d'urgence si votre entreprise comprend plusieurs emplacements entreprise physique.
  
Validation d'une adresse d'urgence consiste à s'assurer qu'il est correctement mis en forme pour les services d'urgence et légitimes. Il est possible de créer et enregistrer une adresse d'urgence n'est pas validée, mais seules les adresses validées peuvent être associés à un utilisateur. Après qu'une adresse d'urgence est validée et enregistrée, il peut être affecté à un utilisateur. Si vous voulez changer l'adresse d'urgence validée enregistré, vous devrez créer un nouveau.
  
## Que sont les emplacements d'urgence ?

Emplacements d'urgence sont associés à une adresse d'urgence pour donner à un emplacement au sein d'une construction plus précis. Un emplacement d'urgence est généralement un étage, construction papillon ou nombre office où se trouve l'utilisateur. Vous pouvez avoir un nombre illimité d'emplacements associés à une adresse d'urgence.
  
Lorsque vous affectez une adresse de secours à un utilisateur, il s'agit en fait d'un ID d'emplacement référencé lors de l'affectation de l'adresse. L'ID d'emplacement inclut l'adresse de secours référencée (la rue ou l'adresse géographique). Un emplacement d'urgence par défaut est inclus avec une adresse de secours au cas où des emplacements internes aux bâtiments ne seraient pas nécessaires. 
  
## Qu'est-ce que le routage d'appel d'urgence ?

Emplacements et les adresses d'urgence sont utilisées pendant le processus d'appels d'urgence routage vers le centre de répartition appropriée lors de l'envoi d'urgence premiers intervenants. Lorsqu'un Skype pour un utilisateur professionnel compose un numéro d'urgence, comment l'appel est acheminé vers le service Public sécurité répondant Point PSAP () varient par pays ou région. Dans certains pays, tels que les États-Unis et le Royaume-Uni, les appels sont tout d'abord être filtrés pour déterminer l'emplacement actuel de l'utilisateur avant de vous connecter à l'appel vers le centre de répartition appropriée. Dans d'autres pays et régions, les appels doivent être routés directement vers le centre d'expédition servant le numéro de téléphone associé à l'appelant d'urgence.
  
## Création, ajout et affecter des emplacements d'urgence et les adresses à vos utilisateurs

1. **Planifier pour les emplacements d'urgence** La première étape consiste à planifier vos emplacements d'urgence. Vous devez répertorier toutes vos adresses physiques. Puis, selon que, déterminez si nécessaire des emplacements pour les adresses d'urgence et dans l'affirmative, ils sont. Par exemple, si une entreprise a 3 office bâtiments chaque avec 4 étages, il est probable qu'il faut 3 adresses d'urgence, avec étages répertoriées sous forme d'un emplacement pour chaque 1 à 4.
    
2. **Création et validation de vos emplacements d'urgence** L'étape suivante consiste à créer et à valider vos adresses de secours. Lorsque vous créez une adresse de secours, vous pouvez la valider. Pour créer une adresse de secours, reportez-vous à la rubrique[Ajout ou suppression d'une adresse d'urgence pour votre organisation](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Valider une adresse postale ou civique consiste à s'assurer qu'il est correctement mis en forme et légitimes. Il est possible qu'une adresse d'urgence partiellement correcte, par exemple un nom de la ville, tapé peut passer toujours passe validation. Le processus de validation utilise toutes les parties d'une adresse donnée pour déterminer si elle contient des informations suffisantes pour acheminer l'appel vers le centre de répartition d'urgence appropriée. Si c'est le cas, il est ramené que validée et puis peut être affectée à un numéro de téléphone. 
  
3. **Obtenir des numéros de téléphone** L'étape suivante consiste à obtenir des numéros de téléphone pour vos utilisateurs. Vous pouvez le faire par obtention des nouveaux numéros de téléphone à partir d'Office 365 ou par « porter » ou de transfert de vos numéros de téléphone existants sur vers Office 365. Pour obtenir la procédure complète, consultez[Transférer des numéros de téléphone vers Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Affecter des numéros de téléphone** La dernière étape consiste à permettre aux utilisateurs de passer et recevoir des appels téléphoniques. Pour ce faire, vous devez affecter un numéro de téléphone à chaque utilisateur. Voir[Affectation, modification ou suppression du numéro de téléphone d'un utilisateur](assign-change-or-remove-a-phone-number-for-a-user.md) pour affecter un numéro de téléphone.
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Skype entreprise Online : appel d'urgence une étiquette d'avis de non-responsabilité](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Conditions générales relatives aux appels d'urgence](emergency-calling-terms-and-conditions.md)
  
[Période de sortant gratuit de audio conférence](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

