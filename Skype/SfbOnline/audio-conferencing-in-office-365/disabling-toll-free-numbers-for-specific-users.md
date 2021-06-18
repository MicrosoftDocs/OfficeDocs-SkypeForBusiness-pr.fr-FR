---
title: Désactivation des numéros gratuits pour des utilisateurs spécifiques de Skype Entreprise Online
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
description: Les administrateurs peuvent contrôler la façon dont les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695679"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Désactivation des numéros gratuits pour des utilisateurs spécifiques de Skype Entreprise Online
 
> [!Note]
> Pour plus d’informations sur la désactivation des numéros gratuits pour les utilisateurs de Teams, voir Désactivation des numéros gratuits [pour certains utilisateurs de Teams.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)

Si votre organisation dispose de numéros gratuits dans son pont de conférence audio Microsoft, vous pouvez autoriser ou empêcher leur utilisation pendant les réunions d’organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont activés pour utiliser des numéros gratuits, ce qui signifie que ces numéros, s’ils sont disponibles, peuvent être utilisés par les participants pour rejoindre leurs réunions. Si ce n’est pas le comportement souhaité pour certains utilisateurs dans votre organisation, vous pouvez restreindre l’utilisation de ces numéros par des utilisateurs spécifiques dans leurs réunions via un contrôle d' enablement de numéro gratuit. 

Lorsque les numéros gratuits sont désactivés pour un organisateur donné : 
 - Un numéro gratuit ne sera plus inclus dans ses invitations aux réunions. 
 - Les numéros gratuits ne seront plus répertoriés dans la page « Rechercher un numéro local » référencé dans ses invitations aux réunions. 
 - Les participants ne pourront pas participer à la réunion de l’organisateur donné s’ils composent un numéro gratuit de l’organisation. 
 - Toutes les réunions de l’organisateur sont automatiquement reprogrammées et le numéro gratuit leur est supprimé.  

    > [!IMPORTANT]
    > Cela renvoye toutes les invitations par courrier électronique de l’organisateur à tous les participants de ces réunions. 

 - Les participants peuvent continuer à rejoindre les réunions de l’organisateur à l’aide de numéros de téléphone. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques 

À partir du **Centre d’administration Microsoft Teams**:

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.

3. Set **Include toll-free numbers in meeting requests from this user** to **Off.** 

4. Cliquez sur **Enregistrer.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Utiliser PowerShell**  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de la cmdlet Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle. Par exemple : 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
