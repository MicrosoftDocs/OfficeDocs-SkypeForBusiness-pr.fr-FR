---
title: Désactivation des numéros de téléphone gratuits pour Skype spécifique pour les utilisateurs professionnels en ligne
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler les organisateurs utilisation numéros gratuits pour leurs réunions.
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229280"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Désactivation des numéros de téléphone gratuits pour Skype spécifique pour les utilisateurs professionnels en ligne
 
> [!Note]
> Pour plus d’informations sur la désactivation numéros sans outil pour les utilisateurs d’équipes, voir [désactivation des numéros gratuits pour les utilisateurs des équipes spécifiques](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Si votre organisation dispose de numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants à participer à des réunions. Si ce n’est pas le comportement souhaité pour certains utilisateurs au sein de votre organisation, vous pouvez empêcher des utilisateurs spécifiques d’à l’aide de ces numéros dans leurs réunions via un contrôle activation du numéro gratuit. 

Lorsque les numéros gratuits sont désactivés pour un organisateur donné : 
 - Un numéro gratuit sera n’est plus inclus dans son ou sa réunion invite. 
 - Numéros gratuits ne sont plus apparaît sur la page « Rechercher un numéro local » qui est référencée dans son ou sa réunion invite. 
 - Les participants ne puissent pas participer à la réunion de l’organisateur donné si elles composer un numéro gratuit de l’organisation. 
 - Replanifier automatiquement toutes les réunions de l’organisateur et le numéro gratuit sera supprimé à partir de celles-ci.  

    > [!IMPORTANT]
    > Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions. 

 - Les participants peuvent poursuivre la participation à des réunions de l’organisateur à l’aide des numéros payants. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques 

À partir du **Centre d’administration de Microsoft équipes**:

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.

3. Pour **désactiver**la valeur **inclure les numéros gratuits dans les demandes de cet utilisateur de réunion** . 

4. Cliquez sur **Enregistrer.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**À l’aide de PowerShell**  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle. Par exemple : 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
