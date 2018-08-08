---
title: Valider votre déploiement Edge dans Skype pour Business Server
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Découvrez comment vérifier que votre déploiement de serveur Edge ou pool de serveurs Edge fonctionne dans Skype pour Business Server.'
ms.openlocfilehash: cb239e2777926796761dd91c1460e1147772a34a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015096"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Valider votre déploiement Edge dans Skype pour Business Server
 
**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou pool de serveurs Edge fonctionne dans Skype pour Business Server.
  
Une fois que vous avez déployé votre serveur Edge ou le pool de serveurs Edge, vous devez savoir si elle fonctionne correctement. Voici quelques éléments qui peuvent aider à vous demandant de confirmer votre environnement Edge est connecté à vos serveurs internes et que vos utilisateurs externes peuvent se connecter à votre Skype pour un environnement Business Server, par le biais de votre serveur Edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge

Alors que la validation de la connectivité est effectuée automatiquement au serveur Edge ou pool de serveurs Edge lorsque les serveurs de périphérie sont installés, vous pouvez toujours confirmer par vous-même avec Windows PowerShell. Exécutez l’applet de commande Get-CsManagementStoreReplicationStatus sur le serveur interne ayant magasin Central de gestion, ou n’importe quel ordinateur du domaine jointes sur le Skype pour Business Server les composants principaux (OcsCore.msi) sont installés.
  
Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Vérification de la connectivité pour vos utilisateurs externes

Nous avons un excellent outil pour confirmer la configuration de votre serveur Edge et la possibilité de se connecter, envoyer et recevoir les messages corrects pour les scénarios de serveur de transport Edge. Il s’agit du [site Anaylzer de connectivité à distance](https://testconnectivity.microsoft.com/). Il s’agit d’un site géré par le service Support technique de Microsoft. Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Éléments à prendre en compte lors du test de connectivité des utilisateurs externes

N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :
  
- Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)
    
- Utilisateurs anonymes.
    
- Utilisateurs de votre organisation qui sont connectés à Skype pour les entreprises à distance, mais ne sont pas à l’aide de VPN.
    
Ces tests déterminera si votre serveur Edge est :
  
- Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
  - Par exemple : telnet sip.contoso.com 443
    
  - Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou le pool de serveurs Edge, en fonction de votre déploiement.
    
- Effectuer une résolution DNS externe précise.
    
  - À partir de l’extérieur de votre réseau, une commande ping chacun des noms de domaines complets externes de votre serveur Edge ou le pool de serveurs Edge. Même si la commande ping échoue, vous verrez les adresses IP que vous pouvez comparer les adresses IP que vous avez précédemment assigné.
    

