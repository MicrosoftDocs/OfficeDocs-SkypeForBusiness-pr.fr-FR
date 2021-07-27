---
title: 'Teams cas Voice Contoso : routage basé sur l’emplacement'
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
description: 'Teams cas de voix pour une entreprise multinationale : routage en fonction de l’emplacement'
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9c63cfc4df61303ce5181c09e7e8b949ffb51b1
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587153"
---
# <a name="contoso-case-study-location-based-routing"></a>Étude de cas Contoso : Location-Based routage

Location-Based routage des appels (LBR) est une fonctionnalité qui restreint la dérivation contre les frais en fonction d’une stratégie et de l’emplacement physique de l’utilisateur au moment du placement ou de la réception d’un appel.  

## <a name="overview"></a>Vue d’ensemble

Contoso a deux bureaux dans un pays où il n’est pas illégal d’ignorer le fournisseur de réseau téléphonique commuté (PSTN) afin de diminuer les coûts des appels longue distance. Le bureau principal dispose d’une connexion Internet qui est utilisée par le bureau principal et par le deuxième bureau. Chaque bureau possède son propre contrôleur de session en bordure (SBC) connecté à un opérateur PSTN.  
 
Dans ce pays, Contoso avait configuré la CBR pour leur déploiement Skype Entreprise réseau. Pour déterminer comment configurer la CBR pour les Teams, Contoso lit plan et Location-Based [routage pour le routage direct.](location-based-routing-plan.md) Contoso a déterminé que Teams et Skype Entreprise suivent les mêmes scénarios lorsque vous pouvez recevoir un appel, quand il peut être reçu, lorsqu’un appel PSTN peut être transféré à un utilisateur Teams et quand vous pouvez transférer un autre utilisateur Teams vers l’appel PSTN.  

Pour Skype Entreprise, LBR a été configurée avec la ligne SIP du contrôleur de session (SBC) qui se connecte à l’opérateur PSTN. Pour ce SBC, Contoso a examiné la liste des [SBC](direct-routing-border-controllers.md) certifiés et déterminé que le déploiement SBC est certifié pour le routage direct, mais n’est pas certifié pour la dérivation média. Pour prendre en charge LBR, le routage direct doit être configuré vers le site SBC, il doit y avoir une sortie Internet locale et le SBC doit être configuré pour la dérivation média. Sur la base de ces informations, Contoso a décidé des choses suivantes :

- Pour retarder l’Teams LBR jusqu’à ce que le SBC existant soit certifié pour la dérivation média.   

- Contoso a décidé d’utiliser le site SBC principal pour l’itinéraire direct vers Office 365.  Le SBC de site principal sera le SBC proxy pour le site distant.  

- Contoso a utilisé un consultant tiers basé en Inde pour participer à la certification de la configuration de la fonction LBR auprès de l’entreprise téléphonique dans le pays.  

- Pour aider les utilisateurs extérieurs au bureau à émettre des appels PSTN, le téléphone mobile émis par l’entreprise a été fourni à leurs employés. 

Les diagrammes suivants montrent les déploiements avant et après pour un pays avec des réglementations téléphoniques nécessitant Location-Based routage :

**Déploiement d’origine**

![Diagramme montrant l’état avant.](media/voice-case-study-5.png)

**Déploiement avec routage direct**

![Diagramme 2 présentant l’état avant.](media/voice-case-study-6.png)


## <a name="configuration"></a>Configuration : 

Pour configurer les composants réseau dans Teams, Contoso a suivi les instructions dans Gérer votre topologie de réseau pour les fonctionnalités [vocales cloud.](manage-your-network-topology.md) Contoso a suivi les étapes ci-dessous pour configurer Location-Based routage : 

- Définir les régions réseau : une région réseau a été définie. 

- Définir les sites réseau - Deux sites réseau ont été définis. Un site pour chaque emplacement de bureau dans la région.

- Définir des sous-réseaux : chaque étage d’un emplacement de bureau possède son propre sous-réseau pour le réseau câblé et sans fil. Cette configuration a permis d’obtenir 20 sous-réseaux pour Contoso. 

- Définir des adresses IP fiables : les adresses IP pour le SBC ont été ajoutées à l’adresse IP de confiance.  

