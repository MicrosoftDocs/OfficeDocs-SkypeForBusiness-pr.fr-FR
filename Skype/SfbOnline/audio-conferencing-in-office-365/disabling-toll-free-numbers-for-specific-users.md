---
title: Désactivation des numéros verts pour des utilisateurs spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Les administrateurs peuvent contrôler comment les organisateurs peuvent utiliser des numéros de téléphone gratuits pour leurs réunions.
ms.openlocfilehash: d0b7703f4dd518caa5ffb339282c5a7bbac4daa3
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactivation des numéros verts pour des utilisateurs spécifiques

Si votre organisation a des numéros gratuits dans son Microsoft Audio Conferencing Bridge, vous pouvez autoriser ou empêcher leur utilisation dans les réunions des organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont activés pour l’utilisation de numéros de téléphone gratuits, ce qui signifie que ces numéros, le cas échéant, peut être utilisé par les participants pour joindre leurs réunions. S’il ne s’agit pas d’un comportement souhaitable pour certains utilisateurs de votre organisation, vous pouvez interdire aux utilisateurs spécifiques à l’aide de ces numéros dans leurs réunions via un contrôle d’activation numéro gratuit. 

Lorsque les numéros verts sont désactivées pour un organisateur donné : 
 - Un numéro d’appel gratuit sera n’est plus inclus dans son ou son invite. 
 - Numéros gratuits ne sont plus apparaît sur la page « Trouver un numéro local » qui est référencée dans son ou son invite. 
 - Les participants ne pourra pas participer à la conférence de l’organisateur donné si elles composer un numéro gratuit de l’organisation. 
 - Toutes les réunions de l’organisateur seront automatiquement replanifiées, et le numéro d’appel gratuit sera supprimé à partir de ceux-ci.  

    > [!IMPORTANT]
    > Cela renvoie toutes les invitations de messagerie de l’organisateur à tous les participants de ces réunions. 

 - Les participants peuvent continuer de participation à des réunions de la bibliothèque multimédia à l’aide des numéros payants. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactivation des numéros verts pour des utilisateurs spécifiques 

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Cliquez sur le menu en regard de **Ponts de conférence**, puis cliquez sur **Modifier** dans la liste déroulante.

4. Dans le volet de **fournisseur de pont de conférence** , désactivez **Autoriser à l’aide des numéros d’appel gratuits dans le pont de conférence de l’organisation à assister aux réunions de cet utilisateur**. 

5. Cliquez sur **Appliquer.** 

Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.

1. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles. 

2. Dans le volet Action, cliquez sur **Modifier**. 

3. Désactivez **Autoriser à l’aide de numéros de téléphone gratuits pour assister aux réunions de cet utilisateur**. 
 
4. Cliquez sur **Enregistrer**. 
 
**Utilisation de PowerShell**  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle. Par exemple : 

 - User@contoso.com Set-CsOnlineDialInConferencingUser-AllowTollFreeDialIn $false
