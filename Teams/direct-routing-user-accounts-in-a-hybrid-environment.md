---
title: Comptes d’utilisateurs dans un environnement hybride avec RTC
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
description: En savoir plus sur les différentes combinaisons de création d’utilisateur et les combinaisons prises en charge ou non prises en charge.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 635ab29498ee01c976b33dc62a193bb723ba190e
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280253"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous disposez de tous les éléments suivants : 
 
- Skype entreprise Server ou Lync Server 2013 
- Une organisation Office 365 
- Connectivité hybride configurée entre le serveur Skype entreprise et Skype entreprise Online ou le client Microsoft teams 
- Utilisateurs autorisés à passer et à recevoir des appels de réseau téléphonique commuté (PSTN) vers et depuis le client

 
Si vous utilisez un autre environnement (par exemple, Skype entreprise version Cloud Connector), le hybride n’est pas configuré, ou vos utilisateurs ne sont pas activés pour les appels RTC, la matrice de prise en charge est différente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>À propos des combinaisons et de la déclaration de prise en charge  

Un environnement hybride Skype entreprise avec connectivité PSTN offre une souplesse qui vous permet de fournir des services d’utilisateur et la manière dont les comptes d’utilisateurs sont approvisionnés et gérés. Toutefois, l’abondance d’options peut créer certaines combinaisons non prises en charge. Cette section décrit les différentes combinaisons de création d’utilisateurs, suivies d’une déclaration de prise en charge.


**Définitions**   
- **Voix entreprise :** Option permettant d’accéder à PSTN pour les utilisateurs disposant d’un compte d’utilisateur Skype entreprise local. Le serveur de médiation Skype entreprise local fournit une interconnexion à PSTN.  
- **Connectivité vocale hybride :** Option permettant d’accéder à PSTN pour les utilisateurs disposant d’un compte Skype entreprise online. Le serveur de médiation Skype entreprise local fournit une interconnexion à PSTN. 
- **Routage direct :** Option permettant d’accéder à PSTN pour les utilisateurs disposant d’un compte Skype entreprise en ligne ou d’une licence Microsoft teams via le client Microsoft Teams. Le SBC est connecté au proxy SIP dans Office 365 sans qu’il soit nécessaire de disposer d’un logiciel local de la part de Microsoft.

  
**L’environnement prend en charge les combinaisons suivantes :**
- **Scénario 1 :** Compte d’utilisateur dans Skype entreprise sur site et utiliser le client Skype entreprise avec Enterprise Voice
- **Scénario 2 :** Compte d’utilisateur dans Skype entreprise Online et utiliser le client Skype entreprise avec une connectivité vocale hybride
- **Scénario 3 :** Compte d’utilisateur dans Skype entreprise Online avec licence Microsoft teams et utiliser le client teams
 
### <a name="supportability-matrix"></a>Matrice de prise en charge


|**Objet utilisateur créé dans**  |**Fournisseur de services Skype entreprise de l’utilisateur**|**Client de l’utilisateur**|**Option voix**|**Prise en charge**|
| ------------ | --------- | --------- | --------- | -------- |
|ANNONCE locale| En local |Skype Entreprise   | Voix Entreprise   |Oui|
|ANNONCE locale|Online| Skype Entreprise  | Connectivité vocale hybride   |Oui |
|ANNONCE locale|Online |Microsoft Teams |Routage direct  |Oui |
|**Combinaisons non prises en charge**    | |         |         |      |
|Azure AD| En local/en ligne | Skype entreprise et Microsoft teams|Voix entreprise/connectivité vocale hybride/routage direct  |Non, un objet utilisateur doit d’abord être créé dans une publicité locale |
|ANNONCE locale  |En local| Microsoft Teams| Voix entreprise/connectivité vocale hybride/routage direct   |Non, le client Microsoft teams n’est pas pris en charge avec Skype entreprise local. |     
|ANNONCE locale  |Online |Skype Entreprise  | Routage direct  |Non, le routage direct n’est pas pris en charge par le client Skype entreprise  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Déclaration de prise en charge pour l’environnement hybride avec RTC

Pour tous les utilisateurs, l’objet utilisateur **doit** être créé dans la publicité locale et synchronisé sur Azure ad à l’aide de l’outil Azure ad Connect. L’activation des utilisateurs pour teams/Skype entreprise **n’est pas prise en charge** si l’objet utilisateur est créé directement dans Azure ad dans une configuration hybride. Pour les nouveaux utilisateurs, tels qu’une nouvelle embauche, qui seront activés directement pour les équipes, l’utilisateur doit être activé pour Skype entreprise à l’aide des outils de gestion Skype entreprise. La création d’utilisateurs en ligne Skype entreprise ou équipes sans les activer dans le pool local avec Enterprise Voice **n’est pas prise en charge**. Pour plus d’informations, [reportez-vous à la configuration du système téléphonique dans Office 365 avec la connectivité PSTN locale dans Skype entreprise Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
