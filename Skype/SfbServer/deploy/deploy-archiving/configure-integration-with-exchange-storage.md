---
title: Configurer l’intégration avec le stockage Exchange pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 'Résumé: cette rubrique vous explique comment configurer l’intégration avec le stockage Exchange dans Skype entreprise Server.'
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234330"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a>Configurer l’intégration avec le stockage Exchange pour Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur la configuration de l’intégration avec le stockage Exchange dans Skype entreprise Server, reportez-vous à cette rubrique.
  
Si vous utilisez l’intégration de Microsoft Exchange pour tous les utilisateurs de votre déploiement, vous n’avez pas besoin de configurer les stratégies d’archivage de Skype entreprise Server pour vos utilisateurs. Au lieu de cela, vous configurez les stratégies de conservation inaltérable pour la prise en charge de l’archivage pour les utilisateurs hébergés sur Exchange, et leurs boîtes aux lettres sont placées dans la conservation inaltérable. Avant de configurer l’intégration avec le stockage Exchange, voir [plan d’archivage dans Skype entreprise Server](../../plan-your-deployment/archiving/archiving.md). Pour plus d’informations sur les stratégies de conservation inaltérable d’Exchange, voir la documentation du produit Exchange. 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a>Configurer l’intégration avec Microsoft Exchange Storage

1. À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 
    
3. Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.
    
4. Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :
    
   - Pour activer l’intégration à Exchange Storage, activez la case à cocher **intégration Microsoft Exchange** .
    
   - Pour désactiver l’intégration à Exchange Storage, décochez la case **intégration de Microsoft Exchange** .
    
5. Cliquez sur **Valider**.
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a>Lorsque Skype entreprise Server et Microsoft Exchange sont déployés dans différentes forêts

Si vous utilisez l’intégration de Microsoft Exchange et que Microsoft Exchange Server n’est pas déployé dans la même forêt que Skype entreprise Server, vous devez vous assurer que les attributs d’annuaire Active Directory suivants sont synchronisés avec la forêt où Skype pour Le déploiement d’Business Server est le suivant:
  
- msExchUserHoldPolicies
    
- proxyAddresses
    
Cet attribut gère plusieurs valeurs. Lorsque vous synchronisez cet attribut, vous devez fusionner les valeurs, et non les remplacer afin de veiller à ce que les valeurs existantes ne soient pas perdues.
  

