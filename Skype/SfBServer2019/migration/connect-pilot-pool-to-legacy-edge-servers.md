---
title: Connexion du pool pilote aux serveurs Edge hérités
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir déployé Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753924"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connexion du pool pilote aux serveurs Edge hérités

Après avoir déployé Skype entreprise Server 2019, vous devez configurer un itinéraire de Fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype entreprise Server 2019 doit être configuré pour utiliser cet itinéraire. 
  
Pour activer le site Skype entreprise Server 2019 afin qu’il utilise le directeur et le serveur Edge du déploiement hérité, utilisez le générateur de topologie pour associer le pool de serveurs Edge hérité.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool Edge hérité à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie. 
    
2. Sélectionnez votre site, qui se trouve directement sous le nœud **Skype entreprise Server** . 
    
3. Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **Itinéraire de fédération**.
    
5. Sous **attribution**de l’itinéraire de Fédération du site, sélectionnez **activer la Fédération SIP**, puis sélectionnez le directeur hérité ou le serveur Edge hérité si aucun directeur n’est mentionné.
  
6. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
7. Dans le générateur de topologie, sous le nœud Skype entreprise Server 2019, naviguez jusqu’aux **Pools frontaux** **Standard Edition Server** ou Enterprise Edition, cliquez avec le bouton droit sur le pool, puis cliquez sur **modifier les propriétés**.
    
8. Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**. 
    
9. Dans la liste, sélectionnez le serveur Edge hérité. 
  
10. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
11. Dans le **Générateur de topologies**, sélectionnez le nœud de niveau supérieur, **Skype entreprise Server**.
    
12. Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.
    
13. Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.
    

