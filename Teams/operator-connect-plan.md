---
title: Connecter
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: En savoir plus sur les Connecter opérateur, tels que la exigences et la planification du déploiement.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adc229264513d7ec4ca692dca1731d7390b80dc243b4571757607c1c76b7cacb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323946"
---
# <a name="plan-for-operator-connect"></a>Planifier l’opérateur Connecter

>[!NOTE]
>L’Connecter est actuellement disponible uniquement en **prévisualisation publique.** La prévisualisation publique vous permet de tester les fonctionnalités à venir et de fournir des commentaires. Les fonctionnalités incluses dans l’aperçu public peuvent ne pas être complètes, subi des modifications et ne sont pas pris en charge dans Office 365 Secteur Public Cloud.

Les Connecter opérateur sont une autre option permettant de fournir une connectivité de réseau téléphonique commuté (PSTN) avec les réseaux Teams réseau Système téléphonique.  

Cet article décrit les avantages et les exigences et répertorie les opérateurs participant au programme Opérateurs Connecter’entreprise.  Si vous décidez que Connecter opérateur est la solution appropriée pour votre organisation, après avoir lu cet article, voir Configurer [l’Connecter.](operator-connect-configure.md)  

## <a name="benefits"></a>Avantages

Avec la Connecter opérateur, si votre opérateur existant participe au programme Connecter de l’opérateur Microsoft, il peut gérer le service de mise à niveau des appels R TEAMS. L’opérateur Connecter fournit les avantages suivants :

- **Tirez parti de contrats existants ou recherchez un nouvel opérateur.** Vous conservez vos opérateurs et contrats préférés, ou choisissez-en un parmi une sélection d’opérateurs participants pour répondre aux besoins de votre entreprise.

- **Infrastructure gérée par un opérateur.** Votre opérateur gère les services d’appel PSTN et les contrôleurs de session en bordure, ce qui vous permet d’économiser sur l’achat et la gestion du matériel.

- **Déploiement plus rapide et plus facile.** Vous pouvez vous connecter rapidement à votre opérateur et attribuer des numéros de téléphone aux utilisateurs, à partir du Centre Teams’administration.

- **Prise en charge et fiabilité améliorées.** Les opérateurs fournissent un support technique et des contrats de niveau de service partagés pour améliorer le service de support, tandis que l’peering direct optimisé par Azure crée une connexion réseau un-à-un pour une fiabilité améliorée.

## <a name="requirements"></a>Conditions requises

 L’Connecter peut être la solution appropriée pour votre organisation si :

- Le plan d’appels Microsoft n’est pas disponible dans votre emplacement géographique.
- Votre opérateur préféré est un participant au programme d’Connecter Microsoft.
- Vous souhaitez trouver un nouvel opérateur pour activer les appels Teams.

Pour activer les affectations de numéros de téléphone à l’Connecter, assurez-vous que vos utilisateurs sont :

- Teams Téléphone licence. Pour plus d’informations, voir [Qu’est-ce Système téléphonique ?](what-is-phone-system-in-office-365.md) et attribuer Teams [des licences de modules Teams aux utilisateurs.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- En mode TeamsOnly. Pour en savoir plus, voir [Comprendre Microsoft Teams et Skype Entreprise coexistence et l’interopérabilité.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="available-operators"></a>Opérateurs disponibles

Les opérateurs suivants sont les participants au programme d’Connecter Microsoft :

| Opérateur | Fonctionnalité | Couverture du pays |
| --- | --- | --- |
| `BT`  | Appel | Belgique, Danemark, Finlande, France, Allemagne, Irlande, Italie, Luxembourg, Pays-Bas, Norvège, Pologne, Afrique du Sud, Espagne, Suède, Suisse, Royaume-Uni |
| `Intrado` | Appel | Belgique, Canada, Danemark, France, Allemagne, Irlande, Luxembourg, Pays-Bas, Espagne, Suède, Royaume-Uni, États-Unis  |
| `NTT`  | Appel | Autriche, Belgique, Brésil, Canada, République tchèque, Danemark, Finlande, France, Irlande, Italie, Luxembourg, Mexique, Pays-Bas, Norvège, Pologne, Portugal, Porto Rico, Roumanie, Afrique du Sud, Espagne, Suède, Suisse, Royaume-Uni, États-Unis |
| `NuWave` | Appel | Autriche, Belgique, Canada, Danemark, France, Allemagne, Irlande, Italie, Pays-Bas, Portugal, Espagne, Suède, Suisse, Royaume-Uni, États-Unis   |
| `Orange Business Services` | Appel | Autriche, Belgique, République tchèque, Danemark, Finlande, France, Guyane française, Allemagne, Guadeloupe, Irlande, Italie, Luxembourg, Martinique, Mayotte, Pays-Bas, Norvège, Pologne, Portugal, Réunion, Saint Martin, Espagne, Svalbard, Suède, Suisse, Royaume-Uni  |
| `Pure IP` | Appel | Australie, Autriche, Belgique, Brésil, Bulgarie, Canada, Chili, Colombie, Croatie, Chypre, Danemark, Finlande, France, Allemagne, Grèce, Hong Kong S.A.R., Irlande, Italie, Japon, Lituanie, Luxembourg, Malaisie, Mexique, Pays-Bas, Norvège, Panama, Pologne, Portugal, Porto Rico, Roumanie, Singapour, Slovaquie, Slovénie, Afrique du Sud, Espagne, Suède, Suisse, Royaume-Uni, États-Unis  |
| `Rogers Business` | Appel | Canada  |
| `TATA Communications` | Appel | Australie, Autriche, Belgique, Canada, République tchèque, Danemark, France, Allemagne, Hong Kong S.A.R., Hongrie, Irlande, Italie, Malaisie, Mexique, Pays-Bas, Pologne, Portugal, Roumanie, Singapour, Corée du Sud, Espagne, Suède, Suisse, Thaïlande, Royaume-Uni, États-Unis |
| `Telekom Deutschland` | Appel | Allemagne  |
| `Telenor` | Appel | Danemark, Finlande, Norvège, Suède  |
| `Verizon` | Appel | États-Unis |
