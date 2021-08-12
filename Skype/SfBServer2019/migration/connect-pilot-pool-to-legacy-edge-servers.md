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
description: Après avoir déployé Skype Entreprise Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype Entreprise Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 8e76dfc9ee99e2c4e82f40d3aba4aa8a43972c98e0569416ce293b2cfc012d96
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296011"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connexion du pool pilote aux serveurs Edge hérités

Après avoir déployé Skype Entreprise Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype Entreprise Server 2019 doit être configuré pour utiliser cet itinéraire. 
  
Pour permettre au site Skype Entreprise Server 2019 d’utiliser le directeur et le serveur Edge du déploiement hérité, utilisez le Générateur de topologie pour associer le pool edge hérité.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool Edge hérité à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie. 
    
2. Sélectionnez votre site, qui se trouve directement sous le **nœud Skype Entreprise Server’accès.** 
    
3. Dans le menu **Actions**, cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **Itinéraire de fédération**.
    
5. Sous **Attribution de l’itinéraire** de fédération du site, sélectionnez Activer la fédération **SIP,** puis sélectionnez le directeur hérité ou le serveur Edge hérité si aucun directeur n’est répertorié.
  
6. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
7. Dans le Générateur de topologie, sous le nœud Skype Entreprise Server 2019, accédez au serveur **Édition Standard** ou aux pools frontux  **Êdition Entreprise,** cliquez avec le bouton droit sur le pool, puis cliquez sur Modifier les propriétés.
    
8. Sous **Associations**, activez la case à cocher en regard de **Associer un pool de serveurs Edge (pour les composants médias)**. 
    
9. Dans la liste, sélectionnez le serveur Edge hérité. 
  
10. Cliquez sur **OK** pour fermer la page **Modifier les propriétés**. 
    
11. Dans **le Générateur de** topologie, sélectionnez le nœud le plus haut, **Skype Entreprise Server**.
    
12. Depuis le menu **Actions**, cliquez sur **Publier la topologie**, puis sur **Suivant**.
    
13. Une fois l’**Assistant Publication** terminé, cliquez sur **Terminer**.
    

