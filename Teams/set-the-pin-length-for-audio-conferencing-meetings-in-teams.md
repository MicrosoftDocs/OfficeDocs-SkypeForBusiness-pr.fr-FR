---
title: Définir la longueur du code confidentiel pour les réunions d’audioconférence
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Découvrez les paramètres de la longueur et des exigences d’un code confidentiel et découvrez comment définir la longueur des réunions dans Microsoft Teams.
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641955"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Définir la longueur du code confidentiel pour les réunions d'audioconférence dans Microsoft Teams

Lorsque vous configurez l’audioconférence pour Microsoft Teams, vous obtenez un pont d’audioconférence. Un pont de conférence peut contenir un ou plusieurs numéros de téléphone. Le numéro de téléphone que vous définissez sera inclus dans les invitations à la réunion pour l’application Microsoft Teams.
  
Le pont de conférence audio répond à l'appel des membres qui sont en cours de connexion à une réunion à l’aide de leur téléphone. Il répond à l’appelant avec des invites vocales d’un standard automatique, puis, selon vos paramètres, peut lire des notifications et demander aux appelants d’enregistrer leur nom. Les **Paramètres de pont de Microsoft** permettent de modifier les paramètres des notifications de réunion et l’expérience d’accès aux réunions, et de définir la longueur des codes confidentiels utilisés par les organisateurs de réunions. Les organisateurs de réunion utilisent des codes confidentiels pour démarrer les réunions s’ils ne peuvent pas participer à la réunion à l’aide de l’application Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Définir la longueur du code confidentiel

Utilisation du Centre d’administration Microsoft Teams :

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont).

3. Dans le volet **Paramètres du pont** , sous **longueur du code confidentiel**, sélectionnez le nombre de chiffres souhaités pour le code confidentiel.

4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Un code confidentiel est différent d'un ID de conférence. Les ID de conférence sont utilisés par les appelants lorsqu'ils rejoignent la réunion. Ils permettent d'identifier la réunion. Le code confidentiel est utilisé pour authentifier un appelant en tant qu'organisateur de la réunion.

## <a name="want-to-know-more-about-pin-settings"></a>Vous souhaitez en savoir plus sur les paramètres du code confidentiel ?

- Les codes confidentiels peuvent être de 4 à 12 chiffres ; la valeur par défaut est 5. Seuls des chiffres doivent être utilisés lors de la création de codes confidentiels. Les lettres et les caractères spéciaux ne sont pas autorisés.

- Un code confidentiel est requis uniquement pour l’organisateur de la réunion lorsqu’un utilisateur Microsoft Teams n’a pas encore démarré la réunion. Si tout le monde compose un numéro pour accéder à la réunion, le code confidentiel est nécessaire pour que l'organisateur puisse commencer la réunion.

- Les paramètres de sécurité de code confidentiel sont appliqués à tous les numéros de téléphone associés à un pont Microsoft. Ils sont appliqués à toutes les réunions qui utilisent les numéros de téléphone associés à un pont spécifique.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[Essayer ou acheter l’audioconférence dans Microsoft 365 pour Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
