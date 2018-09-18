---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Les administrateurs peuvent contrôler si les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions.
ms.openlocfilehash: 6d37fdb6e85f6c1325c4ebea179ad54aab91fa4c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887379"
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

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. En regard de l’option **Audioconférence**, cliquez sur **Modifier**.

4. Désactivez l’option **Include toll-free numbers in meeting requests from this user** (Inclure des numéros gratuits dans les demandes de réunion envoyées par cet utilisateur). 

5. Cliquez sur **Enregistrer**. 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Utiliser Windows PowerShell**  

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
