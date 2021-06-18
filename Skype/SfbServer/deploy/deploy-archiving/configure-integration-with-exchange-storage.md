---
title: Configurer l’intégration avec le stockage Exchange pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé : Lisez cette rubrique pour découvrir comment configurer l’intégration avec le stockage Exchange dans Skype Entreprise Server.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825064"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurer l’intégration avec le stockage Exchange pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment configurer l’intégration avec le stockage Exchange dans Skype Entreprise Server.
  
Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer des stratégies d’archivage Skype Entreprise Server pour vos utilisateurs. Au lieu de cela, vous configurez les stratégies de In-Place Exchange pour prendre en charge l’archivage pour les utilisateurs d’Exchange, dont les boîtes aux lettres sont In-Place archive. Avant de configurer l’intégration avec le stockage Exchange, lisez [Planifier l’archivage dans Skype Entreprise Server.](../../plan-your-deployment/archiving/archiving.md) Pour plus d’informations sur les stratégies de In-Place Exchange, consultez la documentation du produit Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurer l’intégration avec le stockage Microsoft Exchange

1. À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit : .
    
   - Pour activer l’intégration avec le stockage Exchange, activez la case à cocher **Intégration de Microsoft Exchange.**
    
   - Pour désactiver l’intégration avec le stockage Exchange, désactivez la case à cocher **Intégration de Microsoft Exchange.**
    
5. Cliquez sur **Valider**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Quand Skype Entreprise Server et Microsoft Exchange sont déployés dans des forêts différentes

Si vous utilisez l’intégration Microsoft Exchange et que Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype Entreprise Server, vous devez vous assurer que les attributs Exchange Active Directory suivants sont synchronisés avec la forêt où Skype Entreprise Server est déployé :
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.
  

