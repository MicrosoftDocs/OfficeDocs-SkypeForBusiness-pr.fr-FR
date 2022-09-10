---
title: Permettre aux utilisateurs d’enregistrer leur nom pour une réunion
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez comment activer ou désactiver si vos utilisateurs peuvent enregistrer leurs noms lorsqu’ils rejoignent une réunion dans Microsoft Teams.
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641725"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Autoriser les utilisateurs à enregistrer leur nom lorsqu'ils participent à une réunion dans Microsoft Teams

Lorsque vous configurez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez des numéros de téléphone et ce qu’on appelle un pont d’audioconférence. Un pont de conférence peut comporter un ou plusieurs numéros de téléphone qui peuvent être dédiés ou partagés.
  
Le pont de conférence répond à l'appel d’un utilisateur se connectant à une réunion à l’aide de son téléphone. Le pont de conférence répond à l’appelant avec des invites vocales d’un standard automatique, puis, selon ses paramètres, peut lire des notifications, demander aux appelants d’enregistrer leur nom et configurer la sécurité du code confidentiel pour les organisateurs de réunion. Les codes confidentiels sont donnés aux organisateurs de réunions pour leur permettre de démarrer une réunion. Toutefois, vous pouvez le configurer pour qu’un code confidentiel ne soit pas nécessaire pour démarrer une réunion.

## <a name="set-whether-callers-should-record-their-name"></a>Définir si les appelants doivent enregistrer leur nom

Utilisation du Centre d’administration Microsoft Teams :

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Activez ou **désactivez les notifications d’entrée et de sortie de réunion**.

4. Si vous activez les notifications, choisissez **Noms ou numéros de téléphone** sous **type d’annonce Entrée/sortie**, puis **activez Demander aux appelants d’enregistrer leur nom avant de rejoindre une réunion.**

5. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
