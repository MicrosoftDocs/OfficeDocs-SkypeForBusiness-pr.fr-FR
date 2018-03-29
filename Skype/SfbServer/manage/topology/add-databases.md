---
title: Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Résumé : Apprenez à ajouter plus de Skype pour bases de données de serveur de l’entreprise à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server 2015.'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>Ajouter des bases de données à un groupe de disponibilité AlwaysOn dans Skype pour Business Server 2015
 
**Résumé :** Découvrez comment ajouter plusieurs Skype pour bases de données de serveur d’entreprise à un groupe de disponibilité AlwaysOn existant dans Skype pour Business Server 2015.
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>Ajout de bases de données à un groupe de disponibilité AlwaysOn

1. Ouvrez SQL Server Management Studio et accédez au groupe de disponibilité AlwaysOn. Basculer sur le réplica principal.
    
2. Dans le Générateur de topologies, définissez le FQDN de SQL Server du groupe de disponibilité AlwaysOn pour le nom de domaine complet du nœud principal de ce groupe.
    
  - Ouvrir le Générateur de topologies, sélectionnez **Télécharger la topologie de déploiement existant**et cliquez sur **OK**.
    
  - Développez Skype Entreprise Server, développez votre topologie, puis développez **Magasins SQL Server**. Avec le bouton droit de la banque SQL du nouveau groupe de disponibilité AlwaysOn, puis cliquez sur **Modifier les propriétés**.
    
  - Au bas de la page, dans la zone **Nom de domaine complet de SQL Server** , tapez le nom de domaine complet du nœud principal du groupe de disponibilité AlwaysOn.
    
3. Publiez la topologie. Dans le menu **Action**, cliquez sur **Topologie**, puis sur **Publier**. Ensuite, dans la page de confirmation, cliquez sur **Suivant**.
    
4. Pour ajouter la nouvelle base de données pour le groupe de disponibilité AlwaysOn, utilisez SQL Server Management Studio.
    

