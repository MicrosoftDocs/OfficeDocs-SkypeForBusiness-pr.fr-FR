---
title: Comptes d’utilisateur dans un environnement hybride avec RTC
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
description: Découvrez les différentes combinaisons de création d’utilisateurs et les combinaisons prises en charge ou non prises en charge.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676416"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Comptes d’utilisateur dans un environnement hybride avec une connectivité PSTN

## <a name="about-the-environment"></a>À propos de l’environnement

Cet article s’applique aux environnements dans lesquels vous disposez de tous les éléments suivants :

- Skype Entreprise Server ou Lync Server 2013
- Une organisation Microsoft 365 ou Office 365
- Connectivité hybride configurée entre le client Skype Entreprise Server et Skype Entreprise Online ou Microsoft Teams
- Utilisateurs autorisés à passer et recevoir des appels RTC (Public Switched Telephone Network) vers et depuis le client


Si vous avez un environnement différent (par exemple, Skype Entreprise Cloud Connector Edition), que l’environnement hybride n’est pas configuré ou que vos utilisateurs ne sont pas activés pour les appels RTC, la matrice de prise en charge sera différente.

## <a name="about-the-combinations-and-the-supportability-statement"></a>À propos des combinaisons et de l’instruction de prise en charge

Un environnement hybride Skype Entreprise avec connectivité RTC offre une flexibilité quant à l’emplacement où les services utilisateur sont fournis et à la façon dont les comptes d’utilisateur sont approvisionnés et gérés. Mais l’abondance d’options peut créer des combinaisons non prises en charge. Cette section explique différentes combinaisons de création d’utilisateurs, suivies d’une instruction de prise en charge.

**Définitions:**

- **Voix Entreprise :** option permettant d’accorder l’accès à PSTN pour les utilisateurs disposant d’un compte d’utilisateur Skype Entreprise local. Le serveur de médiation Skype Entreprise local fournit une interconnexion avec PSTN.
- **Connectivité vocale hybride :** Option permettant d’accorder l’accès à PSTN pour les utilisateurs disposant d’un compte Skype Entreprise Online. Le serveur de médiation Skype Entreprise local fournit une interconnexion avec PSTN.
- **Routage direct :** Option permettant d’accorder l’accès à PSTN pour les utilisateurs disposant d’un compte Skype Entreprise en ligne, d’une licence Microsoft Teams, à l’aide de Microsoft Teams client. Le SBC est connecté au proxy SIP dans Microsoft 365 ou Office 365 sans avoir besoin de logiciels locaux de Microsoft.

**L’environnement prend en charge les combinaisons suivantes :**

- **Scénario 1 :** Compte d’utilisateur dans Skype Entreprise local et utilisera le client Skype Entreprise avec Voix Entreprise
- **Scénario 2 :** Compte d’utilisateur dans Skype pour les entreprises en ligne et utilisera le client Skype Entreprise avec la connectivité vocale hybride
- **Scénario 3 :** Compte d’utilisateur dans Skype Entreprise en ligne avec une licence Microsoft Teams et utilisera Teams client

### <a name="supportability-matrix"></a>Matrice de prise en charge

|Objet utilisateur créé dans|Fournisseur de services Skype Entreprise de l’utilisateur|Client de l’utilisateur|Option vocale|Pris en charge|
|---|---|---|---|---|
|AD local|En local|Skype Entreprise|Voix Entreprise|Oui|
|AD local|Online|Skype Entreprise|Connectivité vocale hybride|Oui|
|AD local|Online|Microsoft Teams|Routage direct|Oui|
|**Combinaisons non prises en charge**|||||
|Azure AD|Localement/en ligne|Skype Entreprise/Microsoft Teams|Voix Entreprise/connectivité vocale hybride/routage direct|Non, l’objet utilisateur DOIT d’abord être créé dans AD local|
|AD local|En local|Microsoft Teams|Voix Entreprise/connectivité vocale hybride/routage direct|Non, Microsoft Teams client n’est pas pris en charge avec les Skype Entreprise locaux|
|AD local|Online|Skype Entreprise|Routage direct|Non, le routage direct n’est pas pris en charge avec Skype Entreprise client|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instruction de prise en charge de l’environnement hybride avec RTC

Pour tous les utilisateurs, l’objet utilisateur **doit** être créé dans l’AD local et synchronisé avec Azure AD à l’aide de l’outil Connecter Azure AD. L’activation des utilisateurs pour Teams/Skype Entreprise **n’est pas prise en charge** si l’objet utilisateur est créé directement dans Azure AD dans une configuration hybride. Pour les nouveaux utilisateurs, tels qu’un nouvel employé, qui seront activés directement pour Teams, l’utilisateur doit être activé pour Skype Entreprise à l’aide d’outils de gestion Skype Entreprise locaux. La création d’utilisateurs dans des Skype Entreprise ou des Teams en ligne sans les activer dans un pool local avec Voix Entreprise **n’est pas prise en charge**. Pour plus d’informations à ce sujet, consultez [Plan Système téléphonique avec la connectivité RTC locale dans Skype Entreprise Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
