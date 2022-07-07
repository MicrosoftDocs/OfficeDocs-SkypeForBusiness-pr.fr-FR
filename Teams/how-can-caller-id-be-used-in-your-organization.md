---
title: Comment utiliser un ID d'appelant dans votre organisation
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: L’ID d’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs du système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660960"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Comment utiliser un ID d'appelant dans votre organisation

L’ID de l’appelant se compose de deux informations accessibles par l’utilisateur :

- Un numéro de téléphone (appelé CLID ou ID de ligne d’appel). Il s’agit du numéro de réseau téléphonique commuté (RTC) présenté comme l’identification de l’appelant.

- Nom d’un appelant (généralement appelé CNAM). 
  
La fonctionnalité d’ID de l’appelant est disponible pour tous les utilisateurs du système téléphonique, quelle que soit [l’option de connectivité RTC](pstn-connectivity.md) : Plan d’appel Microsoft, Connexion d’opérateur ou Routage direct. 
  
Vous pouvez contrôler l’ID de l’appelant pour les appels entrants et sortants à l’aide d’une stratégie appelée CallingLineIdentity. Pour plus d’informations, consultez [Plus d’informations sur l’ID de ligne et le nom de la partie appelante](more-about-calling-line-id-and-calling-party-name.md).

  
## <a name="outbound-pstn-caller-id"></a>ID d’appelant RTC sortant

Pour l’ID d’appelant PSTN sortant, les options suivantes sont disponibles. 
  
- Numéro de téléphone attribué à l’utilisateur, qui est la valeur par défaut.

- Anonyme, disponible en supprimant la présentation du numéro RTC de l’utilisateur. 

- Un numéro de téléphone de remplacement, qui peut être :

  - Numéro de téléphone classé comme service et numéro gratuit dans l’inventaire des numéros de téléphone de vos forfaits d’appels. Il est affecté à un standard automatique Teams ou à une file d’attente d’appels.

  - Un numéro de téléphone local via le routage direct qui est affecté à un compte de ressource utilisé par un standard automatique Teams ou une file d’attente d’appels. 

- Nom du tiers appelant ou CNAM défini sur l’appel RTC sortant.  
    
Pour plus d’informations, consultez [Définir l’ID d’appelant pour un utilisateur](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle utilisateur final de l’ID d’appelant sortant

Les utilisateurs peuvent remplacer leur paramètre d’ID d’appelant par **Anonyme** en définissant l’attribut EnableUserOverride. 

Si l’ID d’appelant sortant est défini sur Anonymous, enableUserOverride n’a aucun effet et l’ID de l’appelant est toujours défini sur Anonymous. La valeur par défaut de EnableUserOverride est False.

Vos utilisateurs finaux peuvent définir leur ID d’appelant sur Anonyme en accédant à **Paramètres > Appels**, puis, sous **ID de l’appelant**, **sélectionnez Masquer mon numéro de téléphone et mes informations de profil pour tous les appels**. Quelques minutes sont nécessaires pour que ce changement de paramètre reflète les nouveaux appels. 

### <a name="notes"></a>Remarques

Tenez compte des points suivants :

- Vous ne pouvez pas attribuer les types de numéros de téléphone suivants pour l’ID d’appelant sortant :

  - Tous les numéros de téléphone classés en tant qu’utilisateur dans l’inventaire des numéros de téléphone de vos forfaits d’appels.

  - Tout numéro de téléphone local via le routage direct affecté à un utilisateur.

  - Un Skype Entreprise Server numéro de téléphone local.

- L’utilisation de la substitution de numéro de téléphone du compte de ressource fonctionne pour les utilisateurs Teams. La substitution du numéro de téléphone de service fonctionne pour les utilisateurs Teams.

- Le nom de la partie appelante est envoyé aux appels où l’ID de l’appelant est remplacé par LineUri, un numéro de téléphone de service ou de compte de ressource, et lorsque l’appelant est un utilisateur Teams.

- Le nom du tiers appelant peut comporter un maximum de 200 caractères, mais les systèmes en aval peuvent contenir moins de caractères.

- Pour le routage direct, la substitution de numéro de téléphone et le nom de la partie appelante sont envoyés dans l’en-tête FROM SIP. Si le OnlinePstnGateway correspondant est configuré avec ForwardPai = True, l’en-tête SIP P-ASSERTED-IDENTITY contiendra l’utilisateur appelant réel.

- EnableUserOverride est prioritaire sur les autres paramètres de la stratégie, sauf si la substitution est définie sur Anonymous. Par exemple, supposons que l’instance de stratégie a une substitution à l’aide d’un compte de ressource et que EnableUserOverride est défini et activé par l’utilisateur. Dans ce cas, l’ID d’appelant sortant est bloqué et Anonymous est utilisé. Si une instance de stratégie est remplacée par Anonymous et enableUserOverride est définie, l’ID de l’appelant sortant est toujours Anonyme, quel que soit le paramètre de l’utilisateur final.

   
## <a name="inbound-caller-id"></a>ID de l’appelant entrant

Le système téléphonique affiche le numéro de téléphone externe entrant comme ID de l’appelant. Si le numéro est associé à un utilisateur ou à un contact dans Azure AD ou à un contact personnel, les clients Skype Entreprise et Teams affichent l’ID de l’appelant en fonction de ces informations. Si le numéro de téléphone n’est pas dans Azure AD ou un contact personnel, le nom complet fourni par telco s’affiche s’il est disponible.

L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants. Vous pouvez définir cet attribut, mais il n’est pas disponible pour vos utilisateurs finaux sur la page des paramètres utilisateur. Lorsque ce paramètre est activé, l’appelant RTC entrant s’affiche comme provenant d’Anonymous.
  
Pour bloquer l’ID d’appelant entrant, consultez [Définir l’ID de l’appelant pour un utilisateur](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Sujets associés
[Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
