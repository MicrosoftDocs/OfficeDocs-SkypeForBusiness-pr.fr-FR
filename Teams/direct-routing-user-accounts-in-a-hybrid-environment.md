---
title: Comptes d’utilisateurs dans un environnement hybride avec PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez les différentes combinaisons de création d’utilisateurs et les combinaisons qui sont pris en charge ou non.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7b41eb474d7574aa23b5fa195219794ed715424
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690870"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous avez tous les états suivants : 
 
- Skype Entreprise Server ou Lync Server 2013 
- Une organisation Microsoft 365 ou Office 365 
- Connectivité hybride configurée entre le serveur Skype Entreprise et le client Skype Entreprise Online ou Microsoft Teams 
- Utilisateurs activés pour passer et recevoir des appels de réseau téléphonique commuté (PSTN) vers et depuis le client

 
Si vous avez un autre environnement (par exemple, Skype Entreprise, édition Cloud Connector), que le hybride n’est pas configuré ou que vos utilisateurs ne sont pas activés pour les appels PSTN, la matrice de prise en charge sera différente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>À propos des combinaisons et de l’instruction de prise en charge  

Un environnement Skype Entreprise hybride avec connectivité RSTN offre une flexibilité dans les services utilisateur fournis et la manière dont les comptes d’utilisateurs sont approvisionnement et gérés. Mais la plus grande quantité d’options risque de créer des combinaisons non pris en cas de besoin. Cette section explique les différentes combinaisons de création d’utilisateurs, suivies d’une déclaration de prise en charge.


**Définitions :**   
- **Voix Entreprise :** Option de fournir l’accès au réseau PSTN aux utilisateurs avec un compte d’utilisateur Skype Entreprise local. Sur site, le serveur de médiation Skype Entreprise offre une interconnectivité au réseau PSTN.  
- **Connectivité vocale hybride :** Option de fournir l’accès au réseau PSTN pour les utilisateurs utilisant un compte Skype Entreprise Online. Sur site, le serveur de médiation Skype Entreprise offre une interconnectivité au réseau PSTN. 
- **Routage direct :** Option de fournir l’accès au réseau PSTN pour les utilisateurs utilisant un compte Skype Entreprise en ligne, une licence Microsoft Teams, en utilisant le client Microsoft Teams. Le SBC est connecté au proxy SIP dans Microsoft 365 ou Office 365 sans logiciel local de Microsoft.

  
**L’environnement prend en charge les combinaisons suivantes :**
- **Scénario 1 :** Compte utilisateur dans Skype Entreprise local et utilisera le client Skype Entreprise avec les Voix Entreprise
- **Scénario 2 :** Compte d’utilisateur dans Skype Entreprise Online et utilisera le client Skype Entreprise avec Hybrid Voice Connectivity
- **Scénario 3 :** Compte d’utilisateur dans Skype Entreprise Online avec licence Microsoft Teams et utilisera le client Teams
 
### <a name="supportability-matrix"></a>Matrice de prise en charge


|**Objet utilisateur créé dans**  |**Fournisseur de services Skype Entreprise de l’utilisateur**|**Client de l’utilisateur**|**Option Voix**|**Prise en charge**|
| ------------ | --------- | --------- | --------- | -------- |
|AD local| En local |Skype Entreprise   | Voix Entreprise   |Oui|
|AD local|Online| Skype Entreprise  | Hybrid Voice Connectivity   |Oui |
|AD local|Online |Microsoft Teams |Routage direct  |Oui |
|**Combinaisons non pris en place**    | |         |         |      |
|Azure AD| En local/en ligne | Skype Entreprise/Microsoft Teams|Voix Entreprise/Connectivité vocale hybride/routage direct  |Non, l’objet utilisateur DOIT d’abord être créé dans l’AD local |
|AD local  |En local| Microsoft Teams| Voix Entreprise/Connectivité vocale hybride/routage direct   |Non, le client Microsoft Teams n’est pas pris en charge avec Skype Entreprise local |     
|AD local  |Online |Skype Entreprise  | Routage direct  |Non, le routage direct n’est pas pris en charge avec le client Skype Entreprise  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instruction de prise en charge de l’environnement hybride avec PSTN

Pour tous les utilisateurs, l’objet utilisateur doit être créé dans l’AD local et synchronisé avec Azure AD à l’aide de l’outil Azure AD Connect.  L’activation des utilisateurs de Teams/Skype **Entreprise** n’est pas prise en charge si l’objet utilisateur est créé directement dans Azure AD dans une configuration hybride. Pour les nouveaux utilisateurs, tels qu’une nouvelle recrue, qui sera directement activée pour Teams, l’utilisateur doit être activé pour Skype Entreprise à l’aide d’outils de gestion de Skype Entreprise locaux. La création d’utilisateurs dans Skype Entreprise ou Teams en ligne sans les activer au départ dans un pool local avec un Voix Entreprise **n’est pas prise en charge.** Pour plus d’informations, voir Planifier le système téléphonique avec connectivité [PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)sur site dans Skype Entreprise Server.
