---
title: Activer ou désactiver les annonces d’entrée et de sortie des réunions dans Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: L’administrateur peut découvrir comment activer ou désactiver les annonces d’entrée et de sortie dans une réunion Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372203"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Activer ou désactiver les annonces d'entrée et de sortie des réunions dans Microsoft Teams

Lorsque vous configurationnez l’audioconférence dans Microsoft 365 ou Office 365, vous recevez un pont d’audioconférence. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone que les personnes utiliseront pour appeler une réunion Microsoft Teams.
  
Le pont de conférence répond à l’appel d’un utilisateur qui compose un numéro pour accéder à la réunion en utilisant un téléphone. Le pont de conférence répond en utilisant une invite vocale à partir d'un standard automatique, puis, selon vos paramètres, propose des notifications, demande aux appelants d'enregistrer leur nom et fixe la sécurité par code confidentiel. Un code confidentiel est fourni à l’organisateur d’une réunion Microsoft Teams, qui lui permet de démarrer la réunion s’il n’a pas la possibilité de le faire en utilisant l’application Microsoft Teams. Vous pouvez cependant définir les options de telle sorte qu'un code confidentiel ne soit pas nécessaire pour démarrer une réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Définir les options de participation à une réunion

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

Vous devez être un administrateur du service Teams pour apporter ces modifications. Pour en [savoir plus sur l’obtention](https://docs.microsoft.com/microsoftteams/using-admin-roles) de rôles et d’autorisations d’administrateur, voir Utiliser les rôles d’administrateur Teams pour gérer Teams.

1. Connectez-vous au Centre d’administration.

2. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

3. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).

4. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion). Cette option est sélectionnée par défaut. Si vous la désactivez, les utilisateurs qui ont déjà rejoint la réunion ne seront pas informés de l'arrivée ou du départ des autres participants.

5. Sous **Type d'annonce d’entrée/sortie**, sélectionnez **Noms ou numéros de téléphone** ou **Tonalités**.

   > [!NOTE]
   > Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants appelés. Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes).

6. Si vous sélectionnez l'option **Names or phone numbers** (Noms ou numéros de téléphone), activez ou désactivez l’option **Ask callers to record their name before joining the meeting** (Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion).

7. Cliquez sur **Enregistrer**.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous voulez en savoir plus sur Windows PowerShell

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Rubriques connexes

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
