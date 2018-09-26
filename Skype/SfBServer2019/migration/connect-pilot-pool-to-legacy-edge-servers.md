---
title: Connecter le pool pilote aux serveurs Edge hérités
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après avoir déployé Skype pour Business Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype pour Business Server 2019 doit être configuré pour utiliser cet itinéraire.
ms.openlocfilehash: 6766034cf54fd867c9b270324cb1db8ad2d644d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030566"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a>Connecter le pool pilote aux serveurs Edge hérités

Après avoir déployé Skype pour Business Server 2019, vous devez configurer un itinéraire de fédération pour votre site. Pour pouvoir utiliser l’itinéraire fédéré utilisé par l’installation héritée, Skype pour Business Server 2019 doit être configuré pour utiliser cet itinéraire. 
  
Pour activer le Skype pour Business Server 2019 site à utiliser le directeur et le serveur de périphérie du déploiement hérité, utilisez le Générateur de topologie pour associer le pool Edge hérité.
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a>Pour associer le pool Edge hérité à l’aide du Générateur de topologie

1. Ouvrez le Générateur de topologie. 
    
2. Sélectionnez votre site, qui est directement sous le nœud **Skype pour Business Server** . 
    
3. Dans le menu **Actions** , cliquez sur **Modifier les propriétés**.
    
4. Dans le volet gauche, sélectionnez **itinéraire de fédération**.
    
5. Sous **attribution itinéraire de fédération du Site**, sélectionnez **Activer la fédération SIP**, puis sélectionnez le directeur hérité, ou le serveur Edge hérité si aucun directeur n’est répertorié.
  
6. Cliquez sur **OK** pour fermer la page **Modifier les propriétés** . 
    
7. Dans le Générateur de topologie, sous le Skype pour nœud Business Server 2019, accédez au **serveur Standard Edition server** ou **pools frontaux Enterprise Edition**, avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.
    
8. Sous **Associations**, activez la case à cocher en regard de **pool Edge associé (pour les composants multimédias)**. 
    
9. Dans la liste, sélectionnez le serveur Edge hérité. 
  
10. Cliquez sur **OK** pour fermer la page **Modifier les propriétés** . 
    
11. Dans **Le Générateur de topologie**, sélectionnez le nœud de niveau supérieur, **Skype pour Business Server**.
    
12. Dans le menu **Action** , cliquez sur **Publier la topologie**, puis cliquez sur **suivant**.
    
13. Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer**.
    

