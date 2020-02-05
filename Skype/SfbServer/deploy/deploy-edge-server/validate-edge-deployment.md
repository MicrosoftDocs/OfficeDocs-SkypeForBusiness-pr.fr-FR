---
title: Valider votre déploiement Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Découvrez comment vérifier que votre déploiement du serveur Edge Server ou du pool de serveurs Edge fonctionne dans Skype entreprise Server.'
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768297"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Valider votre déploiement Edge dans Skype entreprise Server
 
**Résumé :** Découvrez comment vérifier que votre déploiement du serveur Edge Server ou du pool de serveurs Edge fonctionne dans Skype entreprise Server.
  
Après avoir déployé votre serveur Edge Server ou le pool de serveurs Edge, vous devez savoir s’il fonctionne correctement. Voici quelques conseils qui peuvent vous aider à confirmer la connexion de votre environnement Edge à vos serveurs internes et à la connexion de vos utilisateurs externes à votre environnement Skype entreprise Server via votre périphérie.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Vérification de la connectivité entre vos serveurs internes et vos serveurs Edge

Lorsque la validation de la connectivité est effectuée automatiquement dans un serveur Edge ou un pool de serveurs Edge lorsque les serveurs de périphérie sont installés, vous pouvez toujours confirmer cela avec Windows PowerShell. Exécutez l’applet de construction Get-CsManagementStoreReplicationStatus sur le serveur interne, qui dispose de la Banque centrale de gestion ou de n’importe quel ordinateur sur lequel sont installés les composants principaux de Skype entreprise Server (OcsCore. msi).
  
Le résultat initial de l’exécution de cette commande peut donner un statut False, plutôt que True, pour la réplication. Dans ce cas, exécutez l’applet de commande Invoke-Cs ManagementStoreReplication. Donnez-lui un peu de temps pour terminer la réplication, puis, exécutez à nouveau l’applet de commande Get-Cs ManagementStoreReplicationStatus.
  
## <a name="verify-connectivity-for-your-external-users"></a>Vérification de la connectivité pour vos utilisateurs externes

Nous avons un excellent outil pour confirmer la configuration de votre serveur Edge et la possibilité de vous connecter, d’envoyer et de recevoir les messages appropriés pour les scénarios de serveur Edge. Il s’agit du [site Anaylzer de connexion à distance](https://testconnectivity.microsoft.com/). Il s’agit d’un site géré par le service Support technique de Microsoft. Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario adéquat pour vous.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Éléments à prendre en compte lors du test de connectivité des utilisateurs externes

N’importe quel test pour l’accès des utilisateurs externes doit inclure tous les types d’utilisateurs internes que votre organisation prend en charge, ce qui peut inclure une ou toutes les opérations suivantes :
  
- Utilisateurs d’au moins un domaine fédéré (nous vous recommandons de les tester toutes quand même)
    
- Utilisateurs anonymes.
    
- Les utilisateurs de votre organisation qui sont connectés à Skype entreprise à distance, mais qui ne fonctionnent pas avec VPN.
    
Ces tests déterminent si votre serveur Edge est :
  
- Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
  - Par exemple : telnet sip.contoso.com 443
    
  - Selon votre déploiement, vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou sur le pool de serveurs Edge.
    
- Effectuer une résolution DNS externe précise.
    
  - À partir de l’extérieur de votre réseau, effectuez un test ping sur chacun des noms de domaine complets externes du serveur Edge ou du pool de serveurs Edge. Même si le test échoue, vous verrez les adresses IP, qui vous permettent de comparer les adresses IP que vous avez précédemment affectées.
    

