---
title: Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server.'
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976323"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server
 
**Résumé :** Découvrez comment ajouter plus Skype pour les bases de données Business Server à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Ajout de bases de données à un groupe de disponibilité AlwaysOn

1. Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn. Basculer sur le réplica principal.
    
2. Dans le Générateur de topologie, définissez le nom de domaine complet SQL Server du groupe de disponibilité AlwaysOn sur le nom de domaine complet du nœud principal de ce groupe.
    
  - Ouvrez le Générateur de topologie, sélectionnez **Télécharger la topologie à partir d’un déploiement existant**, cliquez sur **OK**.
    
  - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Cliquez sur le magasin SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.
    
  - En bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez dans le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.
    
3. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.
    

