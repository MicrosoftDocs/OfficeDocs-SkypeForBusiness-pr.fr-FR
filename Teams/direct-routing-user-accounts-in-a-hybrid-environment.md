---
title: Comptes d’utilisateurs dans un environnement hybride avec une connectivité PSTN
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Découvrez les différentes combinaisons de création de l’utilisateur et les combinaisons suivantes sont prises en charge ou non pris en charge.
ms.openlocfilehash: 03fd0f57d4c9f504c2f40d6675e44c8ba96adb13
ms.sourcegitcommit: 2f3d105203edbc21bbbb9c17390b1d3011ef4546
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/27/2018
ms.locfileid: "20084493"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateurs dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous avez tous les éléments suivants : 
 
- Skype pour Business Server 2015 ou de Lync Server 2013 
- Un client Office 365 
- Connectivité hybride configurée entre le Skype pour Business Server et Skype pour client Business en ligne ou des équipes 
- Utilisateurs activés pour émettre et recevoir des appels publics réseau de téléphonique commuté (RTC) et à partir du client

 
Si vous avez un environnement différent (tel que Skype pour l’édition de connecteur Business Cloud), hybride n’est pas configuré, ou vos utilisateurs ne seront pas activés pour les appels RTC, la matrice de prise en charge sera différente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sur les combinaisons et la déclaration de prise en charge  

Un Skype pour un environnement hybride avec une connectivité PSTN flexibilité concernant où les services d’utilisateurs sont fournis et comment les comptes d’utilisateurs sont configurés et gérés. Mais l’abondance des options peut créer certaines combinaisons non pris en charge. Cette section explique les différentes combinaisons de création de l’utilisateur, suivie d’une instruction de prise en charge.


**Définitions de :**   
- **Enterprise Voice :** Option pour fournir l’accès PSTN pour les utilisateurs de Skype locale pour le compte d’utilisateur Business. Skype sur site pour le serveur de médiation Business fournit interconnectivité PSTN.  
- **Connectivité de voix hybride :** Option pour fournir l’accès PSTN pour avec Skype en ligne pour un compte professionnel. Skype sur site pour le serveur de médiation Business fournit interconnectivité PSTN. 
- **Routage direct :** Option pour fournir l’accès PSTN pour les utilisateurs de Skype en ligne pour un compte professionnel, licence Teams Microsoft, à l’aide du client Microsoft Teams. Le contrôleur SBC est connecté au Proxy SIP dans Office 365 sans avoir besoin de n’importe quel logiciel sur site de Microsoft.

  
**L’environnement prend en charge les combinaisons suivantes :**
- **Scénario 1 :** Utilisateur compte dans Skype pour les entreprises dans les locaux et utilisera le Skype pour client d’entreprise avec Enterprise Voice
- **Scénario 2 :** Utilisateur compte dans Skype pour les entreprises en ligne et utilisera le Skype pour client d’entreprise avec connectivité de voix hybride
- **Scénario 3 :** Utilisateur compte dans Skype pour les entreprises en ligne avec licence Microsoft Teams et utilisera le client d’équipes
 
### <a name="supportability-matrix"></a>Matrice de support


|**Objet utilisateur créé dans**  |**Skype l’utilisateur pour le fournisseur de services d’entreprise**|**Client de l’utilisateur**|**Option voix**|**Prise en charge**|
|---------|---------|---------|---------|--------|
|Sur le site AD| En local |Skype Entreprise   | Voix Entreprise   |Oui|
|Sur le site AD|En ligne| Skype Entreprise  | Connectivité de voix hybride   |Oui |
|Sur le site AD|En ligne |Microsoft Teams |Routage direct  |Oui |
|**Combinaisons non pris en charge**    | |         |         |
|Azure AD| Sur le site/en ligne | Skype pour les équipes/Microsoft Business|Enterprise Voice de voix hybride/connectivité/Direct routage  |Non, l’objet utilisateur doit être créé dans AD sur site tout d’abord |
|Sur le site AD  |En local| Microsoft Teams| Enterprise Voice de voix hybride/connectivité/Direct routage   |Non, client Microsoft Teams n’est pas pris en charge avec Skype sur site pour les entreprises |
|Sur le site AD  |En ligne |Skype Entreprise | Routage direct  | Non, Skype pour client d’entreprise n’est pas pris en charge avec le routage Direct  |
|Sur le site AD  |En ligne |Skype Entreprise  | Routage direct  |Non, routage Direct n'est pas pris en charge avec Skype pour Business client et utilisateur doit être activé pour Enterprise Voice sur Skype pour les entreprises tout d’abord  |
|   |         |         |         ||

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Déclaration de prise en charge de l’environnement hybride avec PSTN

Pour tous les utilisateurs, l’utilisateur d’objet **doit** être créé dans l’environnement local AD et synchronisés vers Azure AD à l’aide de l’outil Azure AD se connecter. Activation des utilisateurs pour les équipes/Skype pour l’entreprise **n’est pas pris en charge** si l’objet utilisateur est créé directement dans Azure AD dans une configuration hybride. Pour les nouveaux utilisateurs, par exemple un nouvel employé qui sera activé pour les équipes, l’utilisateur doit être hébergé à l’origine dans Skype pour les entreprises dans les locaux et déplacé vers le serveur d’inscriptions en ligne. Création d’utilisateurs dans Skype en ligne pour les professionnels ou équipes sans premier leur permettant de pool locale avec Enterprise Voice **n’est pas pris en charge**.
  

L’utilisateur doit être activé pour Skype pour les entreprises et à l’aide de Enterprise Voice locaux Skype pour les outils de gestion utilisateur. Activation d’utilisateurs pour Skype pour Business online uniquement **n’est pas pris en charge**. Consultez [cet article](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises) pour plus d’informations sur la façon de permettre aux utilisateurs de Skype pour les entreprises dans configuration hybride.