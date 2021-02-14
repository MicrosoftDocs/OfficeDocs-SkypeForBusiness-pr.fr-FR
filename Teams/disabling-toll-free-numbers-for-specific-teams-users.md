---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez comment contrôler la façon dont les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions pont de conférence audio.
ms.openlocfilehash: 517ffea6a15cd625320f33e3eb4911f4a250d51d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904569"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques

Si votre organisation possède des numéros gratuits dans son pont d’audioconférence Microsoft, vous pouvez autoriser ou interdire leur utilisation dans les réunions d’organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation peuvent utiliser des numéros gratuits, ce qui signifie que si ces numéros sont disponibles, ils peuvent les utiliser pour participer à leurs réunions. Si vous souhaitez que certains utilisateurs de votre organisation ne puissent pas utiliser les numéros gratuits, vous pouvez leur interdire d’utiliser ces numéros dans leurs réunions via une commande d’activation des numéros gratuits. 

Si les numéros gratuits sont désactivés pour un organisateur spécifique : 
 - Un numéro gratuit ne sera plus inclus dans ses invitations à participer à une réunion. 
 - Les numéros gratuits ne seront plus répertoriés sur la page « Rechercher un numéro local » qui est référencée dans ses invitations à participer à une réunion. 
 - Les utilisateurs ne pourront plus participer à la réunion de cet organisateur spécifique s’ils composent un numéro gratuit de leur organisation. 
 - Toutes les réunions de l’organisateur seront replanifiées automatiquement et le numéro gratuit lui sera retiré.  

    > [!IMPORTANT]
    > Tous les courriers électroniques d’invitation de cet organisateur seront renvoyés à tous les participants à ces réunions. 

 - Les utilisateurs peuvent continuer à participer aux réunions de l’organisateur en utilisant des numéros payants. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques 

À partir du **Centre d’administration Microsoft Teams**:

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En regard de l’option **Audioconférence**, cliquez sur **Modifier**.

3. Set **Include toll-free numbers in meeting requests from this user** to **Off.** 

4. Cliquez sur **Enregistrer**. 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Utiliser Windows PowerShell**  

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
