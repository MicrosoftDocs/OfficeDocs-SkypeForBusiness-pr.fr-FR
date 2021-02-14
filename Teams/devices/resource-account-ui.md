---
title: Créer un compte de ressource à l’aide du Centre d’administration Microsoft 365
description: Si vous préférez utiliser une interface utilisateur graphique, vous pouvez créer un compte de ressource pour les salles Microsoft Teams et les barres de collaboration de Microsoft Teams à l’aide du Centre d’administration Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: Créer un compte d’appareil, interface utilisateur de Microsoft 365, Centre d’administration Microsoft 365
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268021"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Créer un compte de ressource Microsoft 365 à l’aide du Centre d’administration Microsoft 365

Les comptes de ressources Microsoft 365 sont des comptes de boîte aux lettres et teams qui sont dédiés à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Par exemple, si vous avez une ressource commune telle qu’une salle de conférence, vous pouvez configurer un compte de ressource pour cette salle de conférence qui acceptera ou refusera automatiquement les invitations aux réunions en fonction de la disponibilité de son calendrier.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Gestion des licences

Avant de créer un compte de ressource Microsoft 365, vérifiez le type de licence dont il a besoin. Si vous comptez uniquement utiliser un compte de ressource pour réserver une ressource (autrement dit, inviter la ressource à votre réunion et l’inviter à accepter ou refuser automatiquement l’invitation), vous n’avez pas besoin d’attribuer une licence à un compte de ressource. Vous devrez attribuer une licence au compte de ressource dans les situations suivantes :

- **Réunion Teams** Si vous souhaitez que la ressource (par exemple, une console salles Microsoft Teams, une barre de collaboration, etc.) participe à une réunion Teams afin que les participants peuvent l’utiliser pour présenter des fichiers vidéo et audio, vous avez besoin d’une licence de salle de réunion. 
- **Appels PSTN** Si vous souhaitez que la ressource passe ou reçoit des appels vers ou depuis un numéro de téléphone externe (appelé un réseau téléphonique commuté public ou un appel RSTN), vous avez besoin d’une licence Microsoft 365 Phone System ou Microsoft 365 Business Voice.

Pour plus d’informations sur les licences Salle de réunion, Système téléphonique et Voix entreprise, consultez [les licences de module](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) complémentaire Microsoft Teams

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Créer un compte de ressource dans le Centre d’administration Microsoft 365

1. Connectez-vous à Microsoft 365 en visitant https://admin.microsoft.com
2. Fournissez les informations d’identification d’administrateur pour votre client Microsoft 365. Vous êtes alors retentra dans votre Centre d’administration Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centre d’administration Microsoft 365":::
3. Dans le Centre d’administration, accédez à Ressources  dans le panneau gauche (vous devrez peut-être sélectionner Afficher tout d’abord), puis sélectionnez Salles **& matériel.** 

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centre d’administration Microsoft 365 - Ressources":::
4. Sélectionnez **Ajouter une boîte aux lettres de ressource** pour créer un compte de salle. Entrez un nom d’affichage et une adresse e-mail pour le compte, **sélectionnez** Ajouter, puis sélectionnez **Fermer.** Nous vous recommandons de standardiser une convention d’affectation de noms pour tous vos comptes de ressources.

> [!NOTE]
> Par défaut, les comptes de ressources sont configurer avec les paramètres suivants. Si vous voulez les modifier, sélectionnez Définir les **options de** planification avant de sélectionner **Fermer.** Si vous souhaitez les modifier ultérieurement, accédez à Ressources Salles & ressource, sélectionnez le compte de ressource, puis sélectionnez Modifier sous  >  Options **de réservation.** 
>
> - Autoriser les réunions répétées
> - Refuser automatiquement les réunions en dehors des limites suivantes
>   - Fenêtre de réservation (jours) : 180
>   - Durée maximale (heures) : 24
> - Accepter automatiquement les demandes de réunion

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centre d’administration Microsoft 365 - Ajouter des ressources":::
5. Accédez à la section **Utilisateurs** du Centre d’administration et, dans la liste **Utilisateurs** actifs, vous verrez la salle que vous vient de créer.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centre d’administration Microsoft 365 - Voir les utilisateurs actifs":::
6. Sélectionnez le nom de la salle pour faire apparaître un panneau des propriétés de compte sur la droite.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centre d’administration Microsoft 365 - Propriétés de l’utilisateur":::
7. Vous devez à présent affecter un mot de passe au compte de ressource. Dans le panneau, vous pouvez voir les propriétés du compte et plusieurs actions facultatives. Sélectionnez **l’icône de la touche** Réinitialiser le mot de passe sous le nom d’utilisateur pour modifier le mot de passe. Désélectionner Exigez que cet utilisateur modifie son mot de passe lors **de sa première se connectant.** Il n’est pas possible de modifier le mot de passe via le processus de inscription de l’appareil. Sélectionnez **Réinitialiser.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centre d’administration Microsoft 365 - Réinitialiser le mot de passe":::
8. Dans la section  **Licences et applications,** définissez l’emplacement de sélection du pays ou de la région d’installation de l’appareil. Faites défiler vers le bas et cochez la case en regard de la licence à attribuer, par exemple Salle de réunion, puis **sélectionnez Enregistrer les modifications.** La licence peut varier en fonction de votre organisation.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centre d’administration Microsoft 365 - Attribuer une licence":::
