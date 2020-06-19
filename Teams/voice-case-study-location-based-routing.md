---
title: Étude de cas de voix contoso teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786008"
---
# <a name="contoso-case-study-location-based-routing"></a>Étude de cas contoso : routage sur site

Le routage de géolocalisation (LBR) est une fonctionnalité qui limite le contournement du péage en fonction de la stratégie et de l’emplacement physique de l’utilisateur au moment du placement ou de la réception d’un appel.  

## <a name="overview"></a>Vue d’ensemble

Contoso possède deux bureaux dans un pays où il est illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) pour réduire les frais d’appel longue distance. Le bureau principal dispose d’une connexion Internet utilisée par le siège social et par le second bureau. Chaque bureau possède son propre contrôleur de bordure de session (SBC) connecté à un opérateur PSTN.  
 
Dans ce pays, contoso avait configuré LBR pour son déploiement Skype entreprise. Pour savoir comment configurer LBR pour Teams, le routage en fonction de l' [emplacement du plan de lecture pour le routage direct](location-based-routing-plan.md)est défini par contoso. Contoso a déterminé que les équipes et Skype entreprise suivent les mêmes scénarios dans le cas où un appel peut être placé, lorsqu’il peut être reçu, qu’un appel RTC peut être transféré à un utilisateur de teams et que vous pouvez transférer un autre utilisateur de teams à l’appel RTC.  

Pour Skype entreprise, LBR a été configuré à l’aide du SIP (session Border Controller) SIP Trunk qui se connecte à l’opérateur PSTN. Pour cette SBC, Contoso a examiné la [liste de SBCS certifiés](direct-routing-border-controllers.md) et déterminé que le SBC déployé est certifié pour le routage direct, mais qu’il n’est pas certifié pour la dérivation multimédia. Pour prendre en charge LBR, le routage direct doit être configuré pour l’SBC sur le site, il doit s’agir d’une sortie Internet locale et l’SBC doit être configuré pour la dérivation de média. En fonction de ces informations, Contoso a décidé ce qui suit :

- Pour retarder l’activation de teams LBR, jusqu’à ce que le SBC actuel soit certifié pour la dérivation multimédia.   

- Contoso a décidé d’utiliser l’SBC site principal pour le routage direct vers Office 365.  L’SBC du site principal sera le proxy SBC pour le site distant.  

- Contoso a utilisé un consultant tiers basé en Inde pour vous aider à certifier la configuration LBR avec la société de téléphonie dans le pays.  

- Pour permettre aux utilisateurs travaillant en dehors du Bureau d’effectuer des appels RTC, le numéro de téléphone mobile émis par la société a été fourni à ses employés. 

Les schémas suivants montrent les déploiements avant et après pour un pays avec des réglementations de téléphonie qui nécessitent un routage sur site :

**Déploiement d’origine**

![Diagramme dont l’État est antérieur](media/voice-case-study-5.png)

**Déploiement avec le routage direct**

![Diagramme dont l’État est antérieur](media/voice-case-study-6.png)


## <a name="configuration"></a>Configurations 

Pour configurer les composants réseau dans Teams, Contoso a suivi les instructions dans [gérer la topologie de votre réseau pour les fonctionnalités vocales de Cloud](manage-your-network-topology.md). Contoso a effectué les étapes ci-dessous pour configurer le routage sur site : 

- Définissez les zones du réseau : une région du réseau a été définie. 

- Définir les sites réseau-deux sites réseau ont été définis. Un site pour chaque emplacement du bureau dans la région.

- Définir des sous-réseaux réseau : chaque étage au sein d’un bureau possède son propre sous-réseau pour le réseau filaire et sans fil. Cette configuration a donné lieu à 20 sous-réseaux pour contoso. 

- Définir des adresses IP approuvées-les adresses IP externes pour les SBC ont été ajoutées à l’adresse IP de confiance.  

