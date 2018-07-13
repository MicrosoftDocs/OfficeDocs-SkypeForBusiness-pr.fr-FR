---
title: Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler les organisateurs utilisation numéros gratuits pour leurs réunions.
ms.openlocfilehash: 2f506163ce815f71d18935040dbf13bf4af4f04c
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20324140"
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques

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

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactivation des numéros de téléphone gratuits pour des utilisateurs spécifiques 

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.

4. Dans le volet de **fournisseur de pont de conférence** , désactivez **Autoriser à l’aide des numéros gratuits dans le pont de conférence de votre organisation à participer à des réunions de cet utilisateur**. 

5. Cliquez sur **s’appliquent.** 

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **les utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles. 

2. Dans le volet Action, cliquez sur **Modifier**. 

3. Désactivez **Autoriser à l’aide des numéros de téléphone gratuits pour participer à des réunions de cet utilisateur**. 
 
4. Cliquez sur **Enregistrer**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**À l’aide de PowerShell**  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle. Par exemple : 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
