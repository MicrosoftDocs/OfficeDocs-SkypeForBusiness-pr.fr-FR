---
title: "Désactivation des numéros verts pour des utilisateurs spécifiques"
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
description: "Les administrateurs peuvent contrôler comment les organisateurs peuvent utiliser des numéros de téléphone gratuits pour leurs réunions."
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
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

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a>Désactivation des numéros verts pour des utilisateurs spécifiques à l’aide de la Skype pour Business admin center 
 1. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**. 
 2. Dans le Skype pour Business admin center dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles. 
 3. Dans le volet Action, cliquez sur **Modifier**. 
 4. Activez ou désactivez **Autoriser l’utilisation des numéros de téléphone gratuits pour assister aux réunions de cet utilisateur**. 
 5. Cliquez sur **Enregistrer**. 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a>Désactivation des numéros verts pour des utilisateurs spécifiques à l’aide de PowerShell  

Vous pouvez utiliser le paramètre AllowTollFreeDialIn de l’applet de commande Set-CsOnlineDialInConferencingUser pour activer ou désactiver ce contrôle. Par exemple : 

 - User@contoso.com Set-CsOnlineDialInConferencingUser-AllowTollFreeDialIn $false
