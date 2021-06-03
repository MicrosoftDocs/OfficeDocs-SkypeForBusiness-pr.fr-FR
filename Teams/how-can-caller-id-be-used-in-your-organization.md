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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: L’ID d’appelant peut être contrôlé pour les appels entrants et sortants pour les utilisateurs Système téléphonique à l’aide d’une stratégie appelée CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723545"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Comment utiliser un ID d'appelant dans votre organisation

L’ID d’appelant se compose de deux informations identifiables :

- Un numéro de téléphone (généralement appelé CLID ou ID de ligne d’appel). Il s’agit du numéro de téléphone commuté public (PSTN) présenté comme identification de l’appelant.

- Nom de l’appelant (généralement appelé CNAM). 
  
La fonctionnalité d’ID d’appelant est disponible pour tous Système téléphonique utilisateurs quelle que soit l’option de connectivité PSTN :

- Forfaits d’appels Microsoft 

- Routage direct via le système téléphonique 
  
Vous pouvez contrôler l’ID d’appelant pour les appels entrants et sortants à l’aide d’une stratégie appelée CallingLineIdentity. Pour plus d’informations, voir [Plus d’informations sur l’ID de ligne d’appel et le nom de l’appelant.](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>ID d’appelant PSTN sortant

Pour l’ID d’appelant PSTN sortant, les options suivantes sont disponibles. 
  
- Numéro de téléphone affecté à l’utilisateur (valeur par défaut).

- Anonyme, disponible en supprimant la présentation du numéro PSTN de l’utilisateur. 

- Un numéro de téléphone de substitution, qui peut être :

  - Un numéro de téléphone classé comme service et numéro gratuit dans l’inventaire de numéros de téléphone de vos forfaits d’appels. Elle est généralement affectée à une Teams Standard automatique ou à une file d’attente d’appels.

  - Un numéro de téléphone local via un routage direct affecté à un compte de ressource utilisé par une Teams Standard automatique ou une file d’attente d’appels. 

- Nom de l’appelant ou nom de l’appelant dans l’appel RSTN sortant.  
    
Pour plus d’informations, [voir Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>Contrôle de l’ID d’appelant sortant par l’utilisateur final

Les utilisateurs peuvent définir leur paramètre d’ID d’appelant sur **Anonyme** en paramètres d’attribut EnableUserOverride. 

Si l’ID d’appelant sortant est définie sur Anonyme, le contrôle EnableUserOverride n’a aucun effet et l’ID d’appelant est toujours définie sur Anonyme. La valeur par défaut de EnableUserOverride est False.

Vos utilisateurs finaux peuvent définir leur ID d’appelant sur Anonyme en sélectionnant **Paramètres > Appels,** puis sous **ID** de l’appelant, sélectionnez Masquer mon numéro de téléphone et les informations de profil pour tous **les appels.**

### <a name="notes"></a>Remarques

Tenez compte des points suivants :

- Vous ne pouvez pas affecter les types suivants de numéros de téléphone à l’ID d’appelant sortant :

  - Les numéros de téléphone classés comme utilisateurs dans l’inventaire de numéros de téléphone de vos forfaits d’appels.

  - Tout numéro de téléphone local via un routage direct affecté à un utilisateur.

  - Un Skype Entreprise Server numéro de téléphone local.

- L’utilisation du substitution de numéros de téléphone de compte de ressource fonctionne uniquement pour Teams utilisateurs. Le remplacement d’un numéro de téléphone de service est disponible pour les Skype Entreprise Ligne et Teams service.

- Le nom de l’appelant n’est envoyé que sur les appels pour lequel l’ID d’appelant remplace LineUri, un numéro de téléphone de compte de service ou de ressource, et lorsque l’appelant est un Teams utilisateur.

- Le nom de l’appelant peut avoir un maximum de 200 caractères, mais les systèmes en aval peuvent prendre en charge moins de caractères.

- Pour un routage direct, le substitution de numéros de téléphone et le nom de l’appelant sont envoyés dans l’en-tête FROM SIP. Si le OnlinePstnGateway correspondant est configuré avec ForwardPai = True, l’en-tête SIP P-ENED-IDENTITY contient l’utilisateur réel de l’appel.

- EnableUserOverride a la préséance sur les autres paramètres de la stratégie, sauf si le remplacement est réglé sur Anonyme. Par exemple, supposons que l’instance de stratégie ait le remplacement à l’aide d’un compte de ressource et qu’EnableUserOverride est définie et activée par l’utilisateur. Dans ce cas, l’ID d’appelant sortant est bloqué et anonyme est utilisé. Si une instance de stratégie a été définie sur Anonyme et EnableUserOverride, l’ID d’appelant sortant sera toujours anonyme, quel que soit le paramètre de l’utilisateur final.

   
## <a name="inbound-caller-id"></a>ID d’appelant entrant

Système téléphonique affiche le numéro de téléphone externe entrant comme ID de l’appelant. Si le numéro est associé à un utilisateur ou à un contact dans Azure AD ou un contact personnel, les clients Skype Entreprise et Teams afficheront l’ID d’appelant sur la base de ces informations. Si le numéro de téléphone n’est pas dans Azure AD ou un contact personnel, le nom complet fourni par le telco s’affiche s’il est disponible.

L'attribut BlockIncomingCallerID permet de bloquer l'ID d'appelant dans les appels RTC entrants. Vous pouvez définir cet attribut, mais il n’est pas disponible pour vos utilisateurs finaux sur la page des paramètres utilisateur. Lorsque ce paramètre est activé, l’appelant PSTN entrant s’affiche comme provenant d’anonyme.
  
Pour bloquer l’ID d’appelant entrant, [consultez Définir l’ID d’appelant d’un utilisateur.](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>Rubriques connexes
[Questions fréquentes à propos du transfert de numéros de téléphone](./phone-number-calling-plans/port-order-overview.md)

[Différents types de numéros de téléphone utilisés pour les offres d'appel](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gérer des numéros de téléphone pour votre entreprise](/microsoftteams/manage-phone-numbers-for-your-organization)

[Conditions générales relatives aux appels d'urgence](./emergency-calling-terms-and-conditions.md)

[Skype Entreprise Online : étiquette d'exclusion de responsabilité pour les appels d'urgence](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
