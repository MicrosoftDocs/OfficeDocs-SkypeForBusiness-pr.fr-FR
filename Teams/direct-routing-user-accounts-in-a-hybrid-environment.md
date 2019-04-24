---
title: Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Découvrez les différentes combinaisons de création de l’utilisateur et les combinaisons suivantes sont prises en charge ou non pris en charge.
ms.openlocfilehash: 88f679d5028cd2626ce4e85f0794aafb38317c9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232618"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous avez tous les éléments suivants : 
 
- Skype pour Business Server ou de Lync Server 2013 
- Un client Office 365 
- Connectivité hybride configurée entre le Skype pour Business Server et Skype pour client Business Online ou Microsoft Teams 
- Utilisateurs activés pour émettre et recevoir des appels publics réseau de téléphonique commuté (RTC) et à partir du client

 
Si vous avez un environnement différent (tel que Skype pour l’édition de connecteur Business Cloud), hybride n’est pas configuré, ou les utilisateurs ne sont pas activés pour les appels RTC, la matrice de prise en charge sera différente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sur les combinaisons et la déclaration de prise en charge  

Un Skype pour un environnement hybride avec une connectivité PSTN flexibilité concernant où les services d’utilisateurs sont fournis et comment les comptes d’utilisateurs sont configurés et gérés. Mais l’abondance des options peut créer certaines combinaisons non pris en charge. Cette section explique les différentes combinaisons de création de l’utilisateur, suivie d’une instruction de prise en charge.


**Définitions de :**   
- **Enterprise Voice :** Option pour fournir l’accès PSTN pour les utilisateurs de Skype locale pour le compte d’utilisateur Business. Skype sur site pour le serveur de médiation Business fournit interconnectivité PSTN.  
- **Connectivité de voix hybride :** Option pour fournir l’accès PSTN pour les utilisateurs de Skype pour un compte Business en ligne. Skype sur site pour le serveur de médiation Business fournit interconnectivité PSTN. 
- **Routage direct :** Option pour fournir l’accès PSTN pour les utilisateurs de Skype en ligne pour un compte professionnel, licence Teams Microsoft, à l’aide du client Microsoft Teams. Le contrôleur SBC est connecté au Proxy SIP dans Office 365 sans avoir besoin de n’importe quel logiciel sur site de Microsoft.

  
**L’environnement prend en charge les combinaisons suivantes :**
- **Scénario 1 :** Utilisateur compte dans Skype pour les professionnels sur site et utilisera le Skype pour client d’entreprise avec Enterprise Voice
- **Scénario 2 :** Utilisateur compte dans Skype pour les entreprises en ligne et utilisera le Skype pour client d’entreprise avec connectivité de voix hybride
- **Scénario 3 :** Utilisateur compte dans Skype pour les entreprises en ligne avec licence Microsoft Teams et utilisera le client d’équipes
 
### <a name="supportability-matrix"></a>Matrice de support


|**Objet utilisateur créé dans**  |**Skype l’utilisateur pour le fournisseur de services d’entreprise**|**Client de l’utilisateur**|**Option voix**|**Prise en charge**|
| ------------ | --------- | --------- | --------- | -------- |
|Sur le site AD| En local |Skype Entreprise   | Voix Entreprise   |Oui|
|Sur le site AD|Online| Skype Entreprise  | Connectivité de voix hybride   |Oui |
|Sur le site AD|Online |Microsoft Teams |Routage direct  |Oui |
|**Combinaisons non pris en charge**    | |         |         |      |
|Azure AD| Sur le site/en ligne | Skype pour les équipes/Microsoft Business|Enterprise Voice de voix hybride/connectivité/Direct routage  |Non, l’objet utilisateur doit être créé dans AD sur site tout d’abord |
|Sur le site AD  |En local| Microsoft Teams| Enterprise Voice de voix hybride/connectivité/Direct routage   |Non, client Microsoft Teams n’est pas pris en charge avec Skype sur site pour les entreprises |     
|Sur le site AD  |Online |Skype Entreprise  | Routage direct  |Non, routage Direct n'est pas pris en charge avec Skype pour Business client et utilisateur doit être activé pour Enterprise Voice sur Skype pour les entreprises tout d’abord  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Déclaration de prise en charge de l’environnement hybride avec PSTN

Pour tous les utilisateurs, l’utilisateur d’objet **doit** être créé dans l’environnement local AD et synchronisés vers Azure AD à l’aide de l’outil Azure AD se connecter. Activation des utilisateurs pour les équipes/Skype pour l’entreprise **n’est pas pris en charge** si l’objet utilisateur est créé directement dans Azure AD dans une configuration hybride. Pour les nouveaux utilisateurs, par exemple un nouvel employé qui sera activé pour les équipes, l’utilisateur doit être activé pour Skype pour l’utilisation de Business localement Skype pour les outils d’administration. Création d’utilisateurs dans Skype en ligne pour les professionnels ou équipes sans premier leur permettant de pool locale avec Enterprise Voice **n’est pas pris en charge**. Pour plus d’informations, recherchez dans le [Plan de système téléphonique dans Office 365 avec une connectivité PSTN dans Skype pour Business Server local](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
