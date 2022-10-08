---
title: Créer des comptes de ressources pour les salles et les appareils Teams partagés
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cet article pour plus d’informations sur la création de comptes de ressources pour les salles et les appareils partagés, notamment les Salles Microsoft Teams, les salles Teams sur Surface Hub et la mise à l’eau à chaud sur les écrans Teams.
ms.openlocfilehash: 1448496137088ce04dc087825e67f7d8b31afd80
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475496"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Créer et configurer des comptes de ressources pour les salles et les appareils Teams partagés

Cet article décrit les étapes de création de comptes de ressources pour les espaces partagés et les appareils, ainsi que les étapes de configuration des comptes de ressources pour Salles Microsoft Teams sur Windows, salles Teams sur Android, salles Teams sur Surface Hub et mise à l’eau à chaud sur les écrans Teams.

Les comptes de ressources Microsoft 365 sont des comptes de boîte aux lettres et teams dédiés à des ressources spécifiques, telles qu’une salle ou un projecteur. Ces comptes de ressources peuvent répondre automatiquement aux invitations aux réunions à l’aide de règles que vous définissez lors de leur création. Par exemple, si vous disposez d’une ressource commune telle qu’une salle de conférence, vous pouvez configurer un compte de ressource pour cette salle de conférence qui acceptera ou refusera automatiquement les invitations aux réunions en fonction de sa disponibilité dans le calendrier. 

Chaque compte de ressource est propre à une seule installation Salles Microsoft Teams ou Teams affiche une implémentation à chaud desking.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> Si vous utilisez des panneaux Microsoft Teams, le compte de ressource salles Teams se connecte aux panneaux Teams salles Teams et associés.

> [!NOTE]
> **Skype Entreprise** <br><br>
> Si vous devez activer votre compte de ressource pour qu’il fonctionne avec Skype Entreprise, consultez [Déployer Salles Microsoft Teams avec Skype Entreprise Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Avant de commencer

### <a name="requirements"></a>Conditions requises

Selon votre environnement, vous avez besoin d’un ou de plusieurs rôles pour créer des comptes de ressources.

|**Environnement**|**Rôles requis**|
|-----|-----|
|Azure Active Directory  <br/> |Administrateur général ou administrateur d’utilisateurs  <br/> |
|Active Directory  <br/> |Administrateurs d’entreprise Active Directory, administrateurs de domaine ou disposant de droits délégués pour créer des utilisateurs. Droits de synchronisation Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrateur général ou administrateur Exchange   <br/> |
|Exchange Server  <br/> |Gestion de l’organisation Exchange ou gestion des destinataires   <br/> |

Si vous créez des comptes de ressources pour salles Teams, l’UPN doit correspondre à l’adresse SMTP du compte de ressource. Consultez [Salles Microsoft Teams exigences](requirements.md) avant de déployer salles Teams.

### <a name="what-license-do-you-need"></a>De quelle licence avez-vous besoin ?

[!INCLUDE [mtr-device-config-license-include](../includes/mtr-device-config-license-include.md)]

## <a name="create-a-resource-account"></a>Créer un compte de ressource

[!INCLUDE [mtr-device-config-account-include](../includes/mtr-device-config-account-include.md)]

## <a name="configure-mailbox-properties"></a>Configurer les propriétés de boîte aux lettres

[!INCLUDE [mtr-device-config-mailbox-include](../includes/mtr-device-config-mailbox-include.md)]

## <a name="turn-off-password-expiration"></a>Désactiver l’expiration du mot de passe

[!INCLUDE [mtr-device-config-password-include](../includes/mtr-device-config-password-include.md)]

## <a name="assign-a-meeting-room-license"></a>Attribuer une licence de salle de réunion

[!INCLUDE [mtr-device-config-assign-include](../includes/mtr-device-config-assign-include.md)]

## <a name="next-steps"></a>Étapes suivantes

### <a name="meeting-policies"></a>Stratégies de réunion

[!INCLUDE [mtr-device-config-policies-include](../includes/mtr-device-config-policies-include.md)]

### <a name="calling"></a>Appel

Il n’existe aucune exigence unique pour activer l’appel avec des comptes de ressources. Vous activez le compte de ressource pour appeler de la même façon que vous activez un utilisateur normal.

> [!NOTE]
> Nous vous recommandons de désactiver la messagerie vocale pour les appareils partagés en affectant une stratégie d’appel aux comptes de ressources d’appareil. Pour plus d’informations, consultez [l’appel et le transfert d’appel dans Teams](../teams-calling-policy.md) .

[!INCLUDE [mtr-device-config-calendar-include](../includes/mtr-device-config-calendar-include.md)]

## <a name="related-articles"></a>Articles connexes

[Configurer des comptes pour Salles Microsoft Teams](rooms-configure-accounts.md)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[licences Salles Microsoft Teams](rooms-licensing.md)
