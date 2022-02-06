---
title: Valider votre déploiement Edge dans Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Résumé : Découvrez comment vérifier que votre déploiement de serveur Edge ou de pool de serveurs Edge fonctionne dans Skype Entreprise Server.'
---

# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>Valider votre déploiement Edge dans Skype Entreprise Server
 
**Résumé :** Découvrez comment vérifier que votre déploiement de serveur Edge ou de pool de serveurs Edge fonctionne dans Skype Entreprise Server.
  
Une fois que vous avez déployé votre serveur Edge ou votre pool de serveurs Edge, vous devez savoir s’il fonctionne correctement. Voici quelques éléments qui peuvent vous aider à confirmer que votre environnement Edge est connecté à vos serveurs internes et que vos utilisateurs externes peuvent se connecter à votre environnement Skype Entreprise Server via votre serveur Edge.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>Vérifier la connectivité entre vos serveurs internes et vos serveurs Edge

Bien que la validation de la connectivité soit effectuée automatiquement dans le serveur Edge ou le pool de serveurs Edge lorsque les serveurs Edge sont installés, vous pouvez toujours le confirmer par vous-même avec Windows PowerShell. Exécutez la cmdlet Get-CsManagementStoreReplicationStatus sur le serveur interne qui possède le magasin central de gestion ou sur tout ordinateur joint au domaine sur lequel Skype Entreprise Server Core Components (OcsCore.msi) sont installés.
  
Le résultat initial de l’exécution de cette commande peut donner un état False, plutôt que True, pour la réplication. Si cela se produit, exécutez Invoke-CsManagementStoreReplication cmdlet. Donnez-lui le temps de terminer la réplication, puis ré-exécutez Get-CsManagementStoreReplicationStatus cmdlet.
  
## <a name="verify-connectivity-for-your-external-users"></a>Vérifier la connectivité de vos utilisateurs externes

Nous avons un excellent outil pour confirmer votre configuration de serveur Edge et la possibilité de se connecter, d’envoyer et de recevoir les messages corrects pour les scénarios de serveur Edge. Il s’agit du [site Analyseur de connectivité à distance](https://testconnectivity.microsoft.com/). Il s’agit d’un site géré et géré par le Support Microsoft. Pour utiliser cet outil, accédez au site web et suivez les instructions pour choisir le scénario à votre place.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>Éléments à prendre en compte lors du test de la connectivité des utilisateurs externes

Tout test d’accès des utilisateurs externes doit inclure chaque type d’utilisateur interne que votre organisation prend en charge, ce qui peut inclure l’une ou l’ensemble des opérations suivantes :
  
- Utilisateurs d’au moins un domaine fédéré (nous vous recommandons toutefois de les tester tous).
    
- Utilisateurs anonymes.
    
- Les utilisateurs de votre organisation qui sont connectés Skype Entreprise à distance, mais n’utilisent pas vpn.
    
Ces tests déterminent si votre serveur Edge est :
  
- Écoute sur les ports requis à l’aide d’un client telnet depuis l’extérieur de votre réseau.
    
  - Par exemple : telnet sip.contoso.com 443
    
  - Vous devez effectuer le test précédent sur les ports que vous utilisez sur votre serveur Edge ou votre pool de serveurs Edge, en fonction de votre déploiement.
    
- Effectuer une résolution DNS externe précise.
    
  - Depuis l’extérieur de votre réseau, testez chacun des FQDN externes de votre serveur Edge ou pool de serveurs Edge. Même si la commande ping échoue, vous verrez les adresses IP, que vous pouvez comparer aux adresses IP que vous avez précédemment affectées.
    

