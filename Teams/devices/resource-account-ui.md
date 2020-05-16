---
title: Créer un compte de ressources à l’aide du centre d’administration 365 Microsoft
description: Si vous préférez utiliser une interface utilisateur graphique, vous pouvez créer un compte de ressources pour vos salles de collaboration et Microsoft teams pour Microsoft teams à l’aide du centre d’administration Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: créer un compte d’appareil, une interface utilisateur Microsoft 365, le centre d’administration Microsoft 365
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Créer un compte de ressources Microsoft 365 à l’aide du centre d’administration Microsoft 365

Le compte de ressources Microsoft 365 est un compte de boîte aux lettres et d’équipe dédié à des ressources spécifiques, telles qu’une salle, un projecteur, etc. Ces comptes de ressources peuvent automatiquement répondre aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Par exemple, si vous disposez d’une ressource commune comme une salle de conférence, vous pouvez configurer un compte de ressources pour cette salle de conférence qui acceptera ou refusera automatiquement les invitations aux réunions en fonction de la disponibilité de celle-ci.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licence

Avant de créer un compte de ressources Microsoft 365, vérifiez le type de licence dont il a besoin. Si vous utilisez uniquement un compte de ressources pour réserver une ressource (c’est-à-dire inviter la ressource à votre réunion et avoir accepté ou refuser automatiquement l’invitation), vous n’avez pas besoin d’attribuer une licence à un compte de ressource. Vous devez attribuer une licence au compte de ressources dans les situations suivantes :

- **Réunion teams** Si vous voulez que la ressource (par exemple, une console Microsoft Teams, une barre de collaboration, etc.) puisse participer à une réunion Teams, afin que les participants puissent l’utiliser pour présenter de la vidéo et du contenu audio, vous avez besoin d’une licence de salle de réunion. 
- **Appels RTC** Si vous voulez que la ressource passe ou recevez des appels vers des numéros de téléphone externes (appelées réseau téléphonique commuté ou appel RTC), vous avez besoin d’un système téléphonique Microsoft 365 ou d’une licence Microsoft 365 Business Voice.

Pour plus d’informations sur la salle de réunion, le système téléphonique et les licences vocales, voir [licences de complément Microsoft teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Créer un compte de ressources dans le centre d’administration 365 Microsoft

1. Connectez-vous à Microsoft 365 en visitanthttps://admin.microsoft.com
2. Fournissez les informations d’identification d’administrateur pour votre client Microsoft 365. Vous serez ainsi dirigé vers le centre d’administration Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Centre d’administration Microsoft 365":::
3. Dans le centre d’administration, accédez à **ressources** dans le volet de gauche (vous devrez peut-être sélectionner commencer **tout** d’abord), puis sélectionnez **salles & Equipement**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Centre d’administration Microsoft 365-ressources":::
4. Sélectionnez **Ajouter une boîte aux lettres de ressources** pour créer un compte de salle. Entrez le nom d’affichage et l’adresse de courrier du compte, puis sélectionnez **Ajouter**, puis **Fermer**. Nous vous recommandons d’utiliser une convention d’affectation de noms pour tous vos comptes de ressources.

> [!NOTE]
> Par défaut, les comptes de ressources sont configurés avec les paramètres suivants. Si vous souhaitez les modifier, sélectionnez **définir les options de planification** avant de sélectionner **Fermer**. Si vous souhaitez les modifier plus tard, accédez à **ressources**  >  **& équipements**, sélectionnez le compte de ressources, puis sélectionnez **modifier** sous **options de réservation**.
>
> - Autoriser la répétition de réunions
> - Refuser automatiquement les réunions en dehors des limites suivantes
>   - Fenêtre de réservation (jours) : 180
>   - Durée maximale (en heures) : 24
> - Accepter automatiquement les demandes de réunion

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Centre d’administration Microsoft 365-ajouter des ressources":::
5. Accédez à la section **utilisateurs** du centre d’administration, puis, dans la liste **utilisateurs actifs** , vous verrez la salle que vous venez de créer.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Centre d’administration Microsoft 365-voir utilisateurs actifs":::
6. Sélectionnez le nom de la salle et le panneau Propriétés du compte s’affiche à droite.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Centre d’administration 365 Microsoft-propriétés utilisateur":::
7. Vous devez à présent affecter un mot de passe au compte de ressources. Dans le panneau, vous pouvez voir les propriétés du compte et plusieurs actions facultatives. Cliquez sur l’icône de **réinitialisation du mot de passe** sous le nom d’utilisateur pour modifier le mot de passe. Désélectionner **demander à cet utilisateur de modifier son mot de passe lors de sa première connexion**. Il n’est pas possible de modifier le mot de passe via le processus de connexion du périphérique. Sélectionnez **Réinitialiser**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Centre d’administration Microsoft 365-réinitialisation du mot de passe":::
8. Dans la section **licences et applications** , définissez l' **option Sélectionner un emplacement** pour le pays ou la région où le périphérique sera installé. Faites défiler vers le bas, puis cochez la case en regard de la licence à attribuer (salle de réunion, par exemple), puis sélectionnez **Save Changes (enregistrer les modifications**). La licence varie en fonction de votre organisation.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Centre d’administration Microsoft 365-attribuer une licence":::
