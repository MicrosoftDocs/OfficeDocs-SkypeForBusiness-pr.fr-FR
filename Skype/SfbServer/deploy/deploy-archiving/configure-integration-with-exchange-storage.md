---
title: Configurer l’intégration avec Exchange stockage de Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer l’intégration avec Exchange stockage dans Skype Entreprise Server.'
ms.openlocfilehash: 3ac2db718057b47ebe214c29e339b94dbc5e63a7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759186"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurer l’intégration avec Exchange stockage de Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’intégration avec Exchange stockage dans Skype Entreprise Server.
  
Si vous utilisez l’intégration Exchange Microsoft pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer Skype Entreprise Server stratégies d’archivage pour vos utilisateurs. Au lieu de cela, vous configurez les stratégies de Exchange In-Place pour prendre en charge l’archivage pour les utilisateurs Exchange, avec leurs boîtes aux lettres mises en In-Place archive. Avant de configurer l’intégration avec Exchange stockage, lisez [Planifier l’archivage dans Skype Entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur Exchange In-Place stratégies de Exchange, consultez la documentation du produit. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurer l’intégration avec le stockage Exchange Microsoft

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit : .
    
   - Pour activer l’intégration avec Exchange stockage, activez la case **à cocher Exchange’intégration** Microsoft.
    
   - Pour désactiver l’intégration avec Exchange stockage, désactivez la case **à cocher Exchange’intégration** Microsoft.
    
5. Cliquez sur **Valider**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Lorsque Skype Entreprise Server et Microsoft Exchange sont déployés dans différentes forêts

Si vous utilisez l’intégration microsoft Exchange et que Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype Entreprise Server, vous devez vous assurer que les attributs Active Directory Exchange suivants sont synchronisés avec la forêt où Skype Entreprise Server est déployé :
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.
  

