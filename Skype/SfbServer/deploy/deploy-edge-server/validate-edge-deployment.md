---
title: Validation du déploiement d’Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Apprenez à vérifier que votre déploiement de serveur Edge ou d’un pool de serveur de transport Edge fonctionne dans Skype pour Business Server 2015.'
ms.openlocfilehash: 02f909310e6b491ae97e31b7013b1307c7688ada
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server-2015"></a>Validation du déploiement d’Edge dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou d’un pool de serveur de transport Edge fonctionne dans Skype pour Business Server 2015.
  
Une fois que vous avez déployé votre serveur Edge ou un pool de serveur de transport Edge, vous devez savoir si elle fonctionne correctement. Voici quelques éléments qui peut vous aider à confirmer votre environnement de bord est connectée à vos serveurs internes, ainsi que vos utilisateurs externes peuvent se connecter à votre Skype pour environnement d’entreprise serveur 2015, passant par le bord.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge

Lors de la validation de la connectivité est effectuée automatiquement dans le serveur de transport Edge ou d’un pool de serveur de transport Edge lorsque les serveurs périphériques sont installés, vous pouvez toujours vérifier par vous-même avec Windows PowerShell. Exécutez l’applet de commande Get-CsManagementStoreReplicationStatus sur le serveur interne qui a la direction centrale de stocker ou de n’importe quel ordinateur faisant partie de domaine sur lequel Skype pour composants de base 2015 Business Server (OcsCore.msi) sont installés.
  
Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Vérification de la connectivité pour vos utilisateurs externes

Nous avons un excellent outil pour la confirmation de votre configuration de serveur de transport Edge et de la possibilité de se connecter, d’envoyer et de recevoir les messages appropriés pour les scénarios de serveur de transport Edge. Il s’agit du [site de Anaylzer de connectivité à distance](https://testconnectivity.microsoft.com/). Il s’agit d’un site géré par le service Support technique de Microsoft. Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Éléments à prendre en compte lors du test de connectivité des utilisateurs externes

N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :
  
- Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)
    
- Utilisateurs anonymes.
    
- Utilisateurs de votre organisation à distance connectés dans Skype pour les entreprises, mais qui ne sont pas à l’aide de VPN.
    
Ces tests détermine si votre serveur de transport Edge est :
  
- Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
  - Par exemple : telnet sip.contoso.com 443
    
  - Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur de transport Edge ou d’un pool de serveur de transport Edge, en fonction de votre déploiement.
    
- Effectuer une résolution DNS externe précise.
    
  - À partir d’à l’extérieur de votre réseau, exécutez ping sur chaque les FQDN externes de votre serveur de transport Edge ou de pool de serveur de transport Edge. Même si la commande ping échoue, vous verrez les adresses IP, ce qui vous pouvez de comparer les adresses IP que vous avez précédemment affecté.
    

