---
title: Teams magasin d’appareils
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: rahulimi
ms.topic: article
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
description: Découvrez comment parcourir et acheter des appareils dans le magasin d’appareils du centre d’administration Teams
ms.openlocfilehash: e5cedb84d50111d90d90d47802f667fb6fdbc106
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045643"
---
# <a name="purchase-devices-in-the-teams-device-store"></a>Acheter des appareils dans le magasin d’appareils Teams

>[!NOTE]
>Le magasin d’appareils Teams est actuellement disponible uniquement en **préversion publique**. La préversion publique vous permet de tester les fonctionnalités à venir et de fournir des commentaires. Les fonctionnalités incluses dans la préversion publique peuvent ne pas être complètes, subir des modifications et ne pas être prises en charge dans Office 365 Secteur Public Cloud.

Le magasin d’appareils du centre d’administration Teams vous permet de parcourir, d’acheter et de provisionner des appareils certifiés pour Microsoft Teams.  

 Pour utiliser le magasin d’appareils dans le centre d’administration Teams, accédez à **Appareils > Store**.

## <a name="requirements"></a>Conditions requises

Pour utiliser le magasin d’appareils, vous devez être administrateur général ou administrateur Teams.

## <a name="browse-the-store"></a>Parcourir le magasin

Le magasin d’appareils comprend tous les appareils certifiés pour Teams, notamment les casques, les caméras web et les appareils Teams tels que les salles Teams, les téléphones de bureau et les écrans Teams. Vous pouvez trier, filtrer ou rechercher l’appareil dont votre organisation a besoin.

## <a name="purchase-devices"></a>Acheter des appareils

Lorsque vous achetez des appareils à partir du magasin d’appareils, le paiement et le traitement, y compris l’expédition et la remise, sont gérés par UnifiedCommunications.com, un partenaire de traitement tiers Microsoft.  

Vous pouvez payer avec une carte de crédit ou un bon de commande. Le paiement du bon de commande nécessite une configuration unique avec le fournisseur de traitement.

Toutes les commandes peuvent être retournées jusqu’à 30 jours après leur livraison.

## <a name="data-handling-and-sharing"></a>Gestion et partage des données

Le magasin d’appareils Teams doit partager les informations de base de l’utilisateur et de l’entreprise, y compris les GUID utilisateur et locataire, avec UnifiedCommunications.com pour permettre l’achat dans le centre d’administration Teams.

Le partage de données est désactivé par défaut. Pour l’activer, accédez au magasin d’appareils Teams, sélectionnez l’icône paramètres, puis activez le paramètre.  

Lorsque ce paramètre est désactivé, les données ne sont pas partagées et vous pouvez parcourir le magasin d’appareils Teams, mais vous ne pouvez pas effectuer d’achats. Les données collectées et partagées avec le fournisseur de traitement pendant que le paramètre était activé sont traitées comme spécifié dans leur déclaration de confidentialité.

## <a name="order-tracking-and-history"></a>Suivi et historique des commandes

Vous pouvez afficher l’historique des commandes en accédant à **l’historique des commandes du Store >**, qui inclut toutes les commandes passées par vous et d’autres administrateurs de l’organisation. L’historique des commandes inclut également l’état d’expédition de vos commandes. Pour toute question sur le suivi des commandes, les retours ou les remboursements, contactez UnifiedCommunications.com. Leurs informations de contact sont disponibles sur la page Historique des commandes.

Les commandes passées dans le magasin d’appareils Teams et toutes les données qui leur sont associées sont classées en tant que commandes de locataire et données de locataire.

## <a name="provision-devices"></a>Provisionner des appareils

Lorsque vous achetez des appareils qui prennent en charge l’approvisionnement à distance, l’adresse MAC de ces appareils est automatiquement ajoutée au centre d’administration Teams lorsque l’appareil est expédié. Selon la commande et le moment de son livraison, l’apparition de l’adresse MAC dans le centre d’administration Teams peut prendre environ 5 jours.

Une fois vos appareils livrés, consultez [Provisionner à distance les appareils](remote-provision-remote-login.md#generate-a-verification-code) pour terminer le processus d’approvisionnement et de connexion.
