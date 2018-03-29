---
title: Configuration de l’intégration avec le stockage Exchange pour Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé : Lisez cette rubrique pour savoir comment configurer l’intégration avec le stockage Exchange dans Skype pour Business Server 2015.'
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a>Configuration de l’intégration avec le stockage Exchange pour Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment configurer l’intégration avec le stockage Exchange dans Skype pour Business Server 2015.
  
Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs dans votre déploiement, vous n’avez pas besoin de configurer Skype pour les stratégies d’archivage de Business Server pour les utilisateurs. Au lieu de cela, vous configurez contenir de Exchange Place des stratégies pour prendre en charge de l’archivage pour les utilisateurs hébergés sur Exchange, avec leurs boîtes aux lettres mis en Place maintenez. Avant de configurer l’intégration avec le stockage Exchange, lire le [Plan pour l’archivage dans Skype pour Business Server 2015](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur les stratégies de contenir sur Place d’Exchange, consultez la documentation du produit Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurer l’intégration avec le stockage de Microsoft Exchange

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :
    
  - Pour activer l’intégration avec le stockage Exchange, activez la case à cocher **intégration de Microsoft Exchange** .
    
  - Pour désactiver l’intégration avec le stockage Exchange, désactivez la case à cocher **intégration de Microsoft Exchange** .
    
5. Cliquez sur **Valider**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Lorsque Skype pour Business Server et Microsoft Exchange sont déployés dans des forêts différentes

Si vous utilisez l’intégration de Microsoft Exchange et Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype pour Business Server, vous devez vous assurer que les attributs Active Directory d’Exchange suivants sont synchronisés à la forêt où Skype pour Business Server est déployé :
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.
  

