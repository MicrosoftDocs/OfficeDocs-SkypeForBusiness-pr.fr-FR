---
title: Désactivation des numéros sans frais pour des utilisateurs spécifiques de Skype entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler la façon dont les organisateurs peuvent utiliser des numéros sans frais pour leurs réunions.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695679"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Désactivation des numéros sans frais pour des utilisateurs spécifiques de Skype entreprise Online
 
> [!Note]
> Pour plus d’informations sur la désactivation des numéros sans outils pour les utilisateurs de Microsoft Teams, voir [Désactiver les numéros sans frais pour des utilisateurs de teams spécifiques](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Si votre organisation utilise des numéros sans frais dans Microsoft audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions d’organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont autorisés à utiliser des numéros sans frais, ce qui signifie que ces numéros, le cas échéant, peuvent être utilisés par les participants pour rejoindre leurs réunions. S’il ne s’agit pas du comportement souhaité pour certains utilisateurs de votre organisation, vous pouvez limiter les utilisateurs spécifiques à l’utilisation de ces numéros dans leurs réunions par le biais d’un contrôle de l’activation d’un numéro gratuit. 

Lorsque les numéros sans frais sont désactivés pour un organisateur donné : 
 - Un numéro gratuit ne sera plus inclus dans ses invitations aux réunions. 
 - Les numéros sans frais ne seront plus indiqués sur la page « Rechercher un numéro local » qui est référencé dans ses invitations aux réunions. 
 - Les participants ne seront pas en mesure de rejoindre la réunion de l’organisateur que vous lui avez fourni s’il compose le numéro sans frais de l’organisation. 
 - Toutes les réunions de l’organisateur seront automatiquement replanifiées et le numéro sans frais sera supprimé.  

    > [!IMPORTANT]
    > Cette opération permet de renvoyer toutes les invitations par courrier électronique de l’organisateur à tous les participants à la réunion. 

 - Les participants peuvent continuer à participer à des réunions de l’organisateur en utilisant des numéros payants. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques 

Dans le **Centre d’administration Microsoft teams**:

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.

3. Définissez **inclure les numéros sans frais dans les demandes de réunion de cet utilisateur** **.** 

4. Cliquez sur **Enregistrer.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utiliser PowerShell**  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-Csonlinedialinconferencinguser n’affiche pour activer ou désactiver ce contrôle. Par exemple : 

- Set-Csonlinedialinconferencinguser n’affiche user@contoso.com – AllowTollFreeDialIn $false
