---
title: Comptes d’utilisateurs dans un environnement hybride avec PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez les différentes combinaisons de création d’utilisateurs et les combinaisons qui sont pris en charge ou non.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 34a531c19ba0b7aebc16b09b360c363eff4a1198
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634848"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous avez tous les états suivants : 
 
- Skype Entreprise Server ou Lync Server 2013 
- Organisation Microsoft 365 ou Office 365 organisation 
- Connectivité hybride configurée entre le client Skype Entreprise Server et Skype Entreprise Online ou Microsoft Teams client 
- Utilisateurs activés pour passer et recevoir des appels de réseau téléphonique commuté (PSTN) vers et depuis le client

 
Si vous avez un environnement différent (par exemple, Skype Entreprise Cloud Connector Edition), que l’environnement hybride n’est pas configuré ou que vos utilisateurs ne sont pas activés pour les appels PSTN, la matrice de prise en charge sera différente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>À propos des combinaisons et de l’instruction de prise en charge  

Un environnement Skype Entreprise hybride avec connectivité RST offre une certaine flexibilité dans les services utilisateur fournis et la manière dont les comptes d’utilisateurs sont approvisionnement et gérés. Mais la plus grande quantité d’options risque de créer des combinaisons non pris en cas de besoin. Cette section explique les différentes combinaisons de création d’utilisateurs, suivies d’une déclaration de prise en charge.


**Définitions :**   
- **Voix Entreprise :** Option de fournir l’accès au réseau PSTN pour les utilisateurs avec un compte d’Skype Entreprise local. Sur site, Skype Entreprise serveur de médiation fournit une interconnexion vers le réseau PSTN.  
- **Connectivité vocale hybride :** Option de fournir l’accès au réseau PSTN pour les utilisateurs Skype Entreprise compte Online. Sur site, Skype Entreprise serveur de médiation fournit une interconnexion vers le réseau PSTN. 
- **Routage direct :** Option de fournir l’accès au réseau PSTN pour les utilisateurs utilisant un compte Skype Entreprise ligne, une licence Microsoft Teams et l’utilisation Microsoft Teams client. Le SBC est connecté au proxy SIP dans Microsoft 365 ou Office 365 sans qu’aucun logiciel local de Microsoft ne soit nécessaire.

  
**L’environnement prend en charge les combinaisons suivantes :**
- **Scénario 1 :** Compte d’utilisateur Skype Entreprise local et utilisera le client Skype Entreprise client avec Voix Entreprise
- **Scénario 2 :** Compte d’utilisateur Skype entreprise en ligne et utilisera le client Skype Entreprise avec Hybrid Voice Connectivity
- **Scénario 3 :** Compte d’utilisateur Skype Entreprise en ligne avec Microsoft Teams licence et utilisera Teams client
 
### <a name="supportability-matrix"></a>Matrice de prise en charge


|**Objet utilisateur créé dans**  |**Fournisseur de services Skype Entreprise’utilisateur**|**Client de l’utilisateur**|**Option Voix**|**Prise en charge**|
| ------------ | --------- | --------- | --------- | -------- |
|AD sur site| En local |Skype Entreprise   | Voix Entreprise   |Oui|
|AD sur site|Online| Skype Entreprise  | Hybrid Voice Connectivity   |Oui |
|AD sur site|Online |Microsoft Teams |Routage direct  |Oui |
|**Combinaisons non pris en place**    | |         |         |      |
|Azure AD| En local/en ligne | Skype Entreprise/Microsoft Teams|Voix Entreprise/Connectivité vocale hybride/routage direct  |Non, l’objet utilisateur DOIT d’abord être créé dans l’AD local |
|AD sur site  |En local| Microsoft Teams| Voix Entreprise/Connectivité vocale hybride/routage direct   |Non, Microsoft Teams client n’est pas pris en charge avec les clients Skype Entreprise |     
|AD sur site  |Online |Skype Entreprise  | Routage direct  |Non, le routage direct n’est pas pris en charge avec Skype Entreprise client  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instruction de prise en charge de l’environnement hybride avec PSTN

Pour tous les utilisateurs, l’objet utilisateur doit être créé dans l’AD local et synchronisé avec Azure AD à l’aide de l’outil de gestion des Connecter Azure AD.  L’activation des utilisateurs Teams/Skype Entreprise  n’est pas prise en charge si l’objet utilisateur est créé directement dans Azure AD dans une configuration hybride. Pour les nouveaux utilisateurs, tels qu’une nouvelle recrue, qui sera directement activée pour Teams, l’utilisateur doit être activé pour Skype Entreprise à l’aide d’outils de gestion Skype Entreprise locaux. La création d’utilisateurs dans Skype Entreprise ou Teams’activation sans les activer au départ dans un pool local avec une Voix Entreprise **n’est pas prise en charge.** Pour plus d’informations à ce sujet, voir Système téléphonique la connectivité [PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)en local dans Skype Entreprise Server.